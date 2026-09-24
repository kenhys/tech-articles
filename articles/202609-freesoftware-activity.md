---
title: "My Free Software Activities in September 2026"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 9月のハイライト

### 9月の活動記録

* 9/2
  * mozc: 3.33.6133+ds1-0.1~exp4が受理されたのでfcitx5-mozcのアイコンの問題調査を実施した
* 9/3
  * mozc: fcitx5-mozcのアイコンの問題を修正して3.33.6133+ds1-0.1~exp5をアップロードした
* 9/5
  * groonga: 16.1.0+dfsg-1をアップロードした
  * gr-framework: 0.73.27+dfsg-1をアップロードした
* 9/6
  * mozc: https://github.com/google/mozc/discussions/1566 画像のオリジナルSVGがないことについてフィードバックした
  * mozc: copyrightやリソースを整理し直した3.33.6133+ds1-0.1~exp6を準備した
* 9/7
  * mozc: https://lists.debian.or.jp/mailman3/hyperkitty/list/debian-devel@debian.or.jp/thread/UGJJBHB3F52FTDSTEGUDAJ3SZ6VX4SUK/
    * mozc 3.33.61.33の動作確認協力者募集のお知らせを投げた
* 9/9
  * fcitx-artwork: https://github.com/fcitx/fcitx-artwork/issues/1
    * fcitx5-mozcで採用したいアイコンのSVGが発掘された。https://github.com/google/mozc/discussions/1566 で画像リソースの問い合わせをしたことから発覚した。
* 9/11
  * mozc: mozcのアイコンリソース周りを点検して修正した
* 9/12
  * fcitx-artwork: https://github.com/fcitx/fcitx-artwork/pull/2
    * sourceとなるSVGのファイル名が間違っていたのでフィードバックした
  * fcitx/mozc: https://github.com/fcitx/mozc/pull/86
    * fcitx5-mozcのtoolActionとconfigToolActionで割り当てられているリソースが同じなのでフィードバックした
* 9/13
  * mozc: リグレッションを修正してmozc-3.33.6133+ds1-0.1~exp9をアップロードした
* 9/14
  * mozc: https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1085173#129
    * ~exp9でほぼ問題を潰したので、unstableへアップロードを計画していることをフィードバックした
* 9/16
  * dh-bazel: https://salsa.debian.org/kenhys/dh-bazel
    * debhelper buildsystemとして使えるdh-bazelを試しに実装してみた
* 9/17
  * dh-bazel: より多くのダミーモジュールをサポート。Mozcもdebian/rulesを多少書き換えてdh-bazelを使ってビルドできるようになった。
* 9/19
  * mozc: 3.33.6133+ds1-0.1~exp10をexperimentalにアップロードした
* 9/20
  * mozc: https://ftp-master.debian.org/deferred.html
    * 3.33.6133+ds1-0.1をunstable向けに15 delayedでアップロードした
* 9/21
  * mozc: debian-devel-jpでGNOME + Wayland + Fcitx5でfirefoxの候補ウィンドウの位置がおかしいというフィードバックの調査。firefox 154以降で修正されているとのことで、fcitx5-mozc側の問題ではないようだった。
  * groonga-normalizer-mysql: 1.3.0-2をアップロードした。testingから削除されてしまった原因はtracker.d.oから追えていない。
* 9/24
  * uim: https://bugs.debian.org/1148870
    * uim自体はgtk4 immoduleをサポートしているのに、uim-gtk4パッケージが提供されていないのでフィードバックした
  * mozc: --with-mozcオプション絡みで、いったんdeferredアップロードしたmozcのパッケージをキャンセルした
