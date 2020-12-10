---
title: "Debian: 在宅勤務するにあたりいまさらやったリモートでの起動・シャットダウンの設定をした話"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

# はじめに

COVID19の影響もあり、ほぼ在宅勤務も珍しくない世相となりました。
これは「生産性向上のための環境整備2020 - 03」の21日目の記事です。

端的にいうと、暗号化ディスクを利用しているDebianをssh経由でリモートからセキュアに起動する環境整備をしました。

# 在宅勤務をするにあたり環境整備で必要だったこと

在宅勤務にあたって、ノートPCであれば自宅に持ち帰って仕事をするということができます。
しかし職場にデスクトップPCを置かざるを得ない場合、リモートから起動したりシャットダウンできる手段が必要になります。

それまでは職場で朝PCの電源を入れ、帰宅時にシャットダウンするようにしていたので、
まったくリモートから操作することを考慮にいれていませんでした。

# Wake on LANという遠隔起動のための手段

幸い、従来からゲートウェイを経由して社内ネットワークには接続できるようになっていました。
そこで利用したのがWake on LANです。

使っているのがDebianなので `wakeonlan` コマンドを利用しました。

```
$ wakeonlan  (MACアドレス)
```

対象となるPCのMACアドレスにマジックパケットを投げつけることにより起動させます。

```
$ sudo ethtool eno1
```

Debianからは `ethtool` を使うとWake on LANが有効になっているか確認できます。

```
MDI-X: on (auto)
Supports Wake-on: pumbg
Wake-on: g
```

ただし、追加でBIOSの`I219 LAN Power On`を有効にしないと手元の環境ではマジックパケットを送りつけても
反応しませんでした。うまくいかないときはBIOSの設定を再確認しましょう。

# PCのディスクを暗号化してあってもパスフレーズを入力してセキュアに起動する

リモートから起動できるようにしても、次の課題は暗号化を解除するパスフレーズの入力です。
これをリモートから行う場合、initramfsに細工してあげる必要があります。
次のようにdropbearを利用します。

## dropbearのインストールと鍵の設定

dropbearを利用するので必要なパッケージをインストールします。

```
sudo apt install dropbear busybox
```

次に、`authorized_key` を配置します。

```
/etc/dropbear-initramfs/authorized_keys
```

そのあと、initramfsを作り直します。

```
$ sudo update-initramfs -u
```

## IPアドレスの指定

PCに固定のIPを割り振るようにしているので、`/etc/default/grub` を以下のように変更します。

```
GRUB_CMDLINE_LINUX="ip=(固定IP)::192.168.10.1:255.255.255.0::eno1:none"
```

設定ファイルを書き換えたら、GRUBを更新します。

```
$ sudo update-grub
```

## リモートから起動してみる

ここまでできたら、いったんシャットダウンします。
Wake on LANでinitramfsを起動した状態でssh経由でログインできます。


あとは `crypt-unlock` でパスフレーズを入力します。

```
# crypt-unlock
```


ここでいったんsshの接続がきれ、通常の起動シーケンスでたちあがります。


# dropbearとopensshの鍵を揃えるには

これだけだと、dropbearとopensshとでホストのフィンガープリントが異なってしまっています。
IPアドレスが一緒で、フィンガープリントが異なっているとsshで接続するときに面倒なので
opensshのホスト鍵にそろえてしまいましょう。

```
$ sudo rm -f /etc/dropbear-initramfs/dropbear_dss_host_key
$ sudo dropbearconvert openssh dropbear /etc/ssh/ssh_host_ecds_key /etc/dropbear-initramfs/dropbear_ecdsa_host_key
$ sudo dropbearconvert openssh dropbear /etc/ssh/ssh_host_ed25519_key /etc/dropbear-initramfs/dropbear_ed25519_host_key
$ sudo dropbearconvert openssh dropbear /etc/ssh/ssh_host_rsa_key /etc/dropbear-initramfs/dropbear_rsa_host_key
```

dropbear_dss_host_keyに対応するものはないので削除しています。なくても問題ないです。
念の為、sudo update-initramfs -uしなおします。

### まとめ

今回は暗号化ディスクを利用しているDebianをssh経由でリモートからセキュアに起動する環境整備の方法を紹介しました。
22日目は「」だそうです。

# 参考

* [暗号化ディスクのcrypt-unlock をSSH経由でして、ロック解除する](https://takuya-1st.hatenablog.jp/entry/2019/09/27/025245)
