---
title: "ConoHa VPS (v3)にDebianをインストールする方法(2024年1月時点)"
emoji: "🪔"
type: "tech"
topics: ["Debian", "Linux"]
published: true
---


本記事はConoHa VPS (v3)でDebianのインスタンスを立てようとおもったら、標準イメージにDebianがなくて切ない思いをしたひとのための記事です。

[ひとりしずかに。- ConoHa (v3)にDebianをインストールする方法(2024年1月時点)](https://kenhys.hatenablog.jp/entry/2024/01/14/171628)とのクロス
ポスト記事です。

[2024/01/20(土)のDebian勉強会(オンライン開催)](https://debianjp.connpass.com/event/306126)で、本記事の内容を発表予定です。


# はじめに

ConoHa VPSには従来のv2に加えて、v3という異なるインフラのサービス群が昨年追加されました。
v2では標準イメージとしてDebianを選択することができましたが、v3では標準イメージとしてUbuntuは選択できるもののDebianはありません。
~~OpenBSDとかNetBSDとかFreeBSDはあるのに。~~

しかし、各種APIは提供されているのでそれを使えばなんとかなりそうです。

なお、[ご利用ガイド CLIツールで簡単にISOイメージをマウントする](https://support.conoha.jp/v/clitools/)はv2向けっぽいのでv3では利用できません。


# ISOイメージをつかってインストールするには

公式ドキュメントにISOイメージを使ってインストールする方法が案内されています。

[APIでVPSにISOイメージを挿入する](https://doc.conoha.jp/api-vps3/api-mount_iso_image-v3/)

上記手順に従って作業すればDebianをインストールすることが可能です。やったね。

Debian bookworm 12.4.0の[netinst.iso](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-12.4.0-amd64-netinst.iso)あたりをダウンロードしてきて使うと良いでしょう。

# カスタムISOを使ってインストールしたい

なお、Debian公式イメージを使ってインストールする場合、ConoHa 標準イメージを利用した場合のように次のことができません。

* 初期構築の時点でsshの公開鍵認証を使う

パスワード認証でsshとかもうやりたくないですよね。最初から公開鍵認証にしたい。

# カスタムISOイメージをつくる

ようは事前に公開鍵認証のための設定を仕込んでいけばよいわけです。

* preseed.cfg
* [FAI (Fully Automated Installer)](https://fai-project.org/)
* [simple-cdd](https://wiki.debian.org/Simple-CDD)

自動化のためのソリューションはいろいろあるようです。
お好きなものを選択するのが良いでしょう。

本記事では、preseed.cfgをCDイメージに含めて参照するfile preseedについて説明します。


前提条件は「1 core 512MBの最小スペックのDebianインスタンスを構築し、公開鍵認証でログインできるようにする」です。
インストール時には全部自動化まではできなくてもよいものとします。(きちんと作り込むのがちょっと面倒くさいので)

なお、初期イメージとしてUbuntu 22.04を選択すると最小スペックの512MBのインスタンスは使えません。Ubuntu 20.04を選択しましょう。

## 事前準備

まずは、CDイメージの中身をとりだしておきます。

```bash
sudo mount -o loop debian-12.4.0-amd64-netinst.iso /media/cdrom
sudo cp -r /media/cdrom rootfs
sudo chown $(USER):$(USER) -R rootfs
sudo umount /media/cdrom
```

あとはこれをcustom-isoとしてコピーしてそっちをいじります。

## Graphical Installを無効化する

デフォルトではGUIインストーラーを起動しようとするのであらかじめ殺しておきます。512MBではテキストモードでのインストール一択です。

```diff
diff --git a/isolinux/menu.cfg b/isolinux/menu.cfg
index 2b89df3..f8e961a 100644
--- a/isolinux/menu.cfg
+++ b/isolinux/menu.cfg
@@ -3,7 +3,7 @@ menu width 70
 
 menu title Debian GNU/Linux installer menu (BIOS mode)
 include stdmenu.cfg
-include gtk.cfg
+#include gtk.cfg
 include txt.cfg
 menu begin advanced
     menu label ^Advanced options
```


## テキストモードの選択と、リージョンなどの質問をスキップする

うっかり、他のモードでインストールが始まらないように、テキストモードをデフォルトにしておきます。

```diff
diff --git a/isolinux/txt.cfg b/isolinux/txt.cfg
old mode 100644
new mode 100755
index 4bec49c..794be48
--- a/isolinux/txt.cfg
+++ b/isolinux/txt.cfg
@@ -1,4 +1,5 @@
 label install
        menu label ^Install
+       menu default
        kernel /install.amd/vmlinuz
-       append vga=788 initrd=/install.amd/initrd.gz --- quiet 
+       append language=en country=US keymap=us file=/cdrom/preseed/preseed.cfg vga=788 initrd=/install.amd/initrd.gz --- quiet 
```

また、起動時のパラメーターでインストール中の言語やキーマップの選択をスキップできるようにします。

他の質問をスキップするために、file=/cdrom/preseed/preseed.cfgを読み込むように指示しておきましょう。
あとは、preseed.cfgがうまく作り込めていればテキストモードでの質問にいちいち答えなくてもいいわけです。

## preseed.cfgで公開鍵認証を有効にする

```
# Setup public key
d-i preseed/late_command string \
  cp /cdrom/preseed/sshd_config.d.local /target/etc/ssh/sshd_config.d/local.conf ; \
  mkdir -p /target/home/debian/.ssh ; \
  cp /cdrom/preseed/authorized_keys /target/home/debian/.ssh/ ; \
  in-target chown debian:debian -R /home/debian/.ssh ; \
  in-target chmod 400 /home/debian/.ssh/authorized_keys
```

preseed.cfgの最後のあたりに上記のような設定を追加します。
あらかじめdebianユーザーがpreseed.cfgによって作成してあって、そのauthorized_keysを設定するという想定の記述例です。

sshdの設定もCDイメージに含めておけば、上記のようにして一緒に仕込んでおくこともできます。

## CDのコンテンツのチェックサムを更新する

```
cd custom-iso; \
sudo chmod +w md5sum.txt; \
find -follow -type f ! -name md5sum.txt -print0 | xargs -0 md5sum > md5sum.txt; \
sudo chmod -w md5sum.txt
```
CDイメージに含めるファイルを書き換えているので、チェックサムを更新しておきます。

## リマスタリングCD

```
sudo genisoimage -quiet -r -J -b isolinux/isolinux.bin -c isolinux/boot.cat -no-emul-boot -boot-load-size 4 -boot-info-table -o netinst.iso custom-iso
```

作業しているディレクトリがcustom-isoだとしたら、その親ディレクトリでコマンドを実行してnetinst.isoを生成します。
(`-b`や`-c`オプションに指定しているisolinux/isolinux.binなどは親ディレクトリに存在していなくて支障ありません。)


# さいごに

本記事は、ConoHa VPS (v3)で標準イメージとしてDebianが選択できるようになったら役割を終える内容です。
賞味期限がたぶん短いはずなので試すならお早めに。(標準イメージとしてDebianが利用できるならわざわざこんなことしなくてもよいためです。)


この記事はUltimate Hacking Keyboard v2で執筆しました。
