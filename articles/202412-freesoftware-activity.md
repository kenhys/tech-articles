---
title: "My Free Software Activities in December 2024"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 12月のハイライト

### 12月の活動記録

* 12/4
  * https://qiita.com/advent-calendar/2024/debian
    * Debian Advent Calendar 2024に参加。今年踏んだ不具合記事を公開した。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1085173#30
    * mozc: experimentalのパッケージだとuim-mozcの挙動に問題がある旨をフィードバック
* 12/5
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1085173#50
    * mozc: uim-mozcの挙動に問題がある件wayland環境でのみ発生することをフィードバック
  * mozc: mozc_2.29.5160.102+dfsg-1をDELAYED Queue (15-days)としてアップロードした
* 12/8
  * https://github.com/DIGImend/digimend-kernel-drivers/pull/707
    * digimend: 6.11もサポートするようにフィードバックしておいた
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1089494
    * digimend: 6.12でFTBFSの報告があったので13-2をアップロードしておいた
* 12/10
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1089622
    * protobuf: experimentalのパッケージが投入された場合の影響を調べてフィードバックした
  * gr-framework: 0.73.9がリリースされていたのでパッケージをアップロードした
  * https://github.com/sciapp/gr/pull/193
    * gr-frameworkをパッケージングしていて気づいたtypoをフィードバックした
* 12/15
  * あんどきゅめんてっどでびあん2024冬号の原稿(tag2upload)
* 12/16
  * あんどきゅめんてっどでびあん2024冬号の原稿(Mozc)
* 12/20
  * https://salsa.debian.org/debian/mozc/-/merge_requests/11
    * mozc: source after successful buildの問題を修正
* 12/21
  * Debian勉強会に参加
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1045435
    * mozc: 関連バグを含めてdelayedアップロードして修正するつもりをフィードバック
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1049806
    * mozc: binaryについては#1045435を修正したら同時に修正された模様
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1050420
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1059962
    * mozc: loong64についてはshenzou.d.nでビルドできることを確認済みなので一緒に修正してnmuを出すつもり
    * delayed/10としてdeferredアップロードしておいた
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1090920
    * digimend-dkms: バグ報告があったのでフィードバックしておいた。rebindしなくした影響かもしれない。
* 12/22
  * digimend-dkms: /usr/share配下の設定ファイルを上書きしないように修正して13-4をアップロードした
