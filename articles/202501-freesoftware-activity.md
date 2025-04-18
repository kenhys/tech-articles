---
title: "My Free Software Activities in January 2025"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 1月のハイライト

1月は、d-iの修正に注力したが、メンテナであるCyrilさんがみてくれるということなので
あとはおまかせした。

deskflowはnew queueに滞留していてレビュー待ちが続いているうちに、v1.18.0がリリースされてしまった。
再度、v1.18.0向けにパッケージングをしなおしている。

今年はDebian 13が夏ぐらいにはリリースされるはずで、d-iの日本語の問題を解決したものを
リリースしておきたい。

### 1月の活動記録

* 1/1
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1085173
    * mozc: mozcの2.29.5268.102に更新するために必要な情報に関してフィードバックしておいた
* 1/3
  * https://salsa.debian.org/installer-team/rootskel-gtk/-/merge_requests/5
    * rootskel-gtk: デフォルトのフォントをMotoyaLCedarを採用するように変更した
  * https://salsa.debian.org/fonts-team/fonts-morisawa-bizud-gothic/-/merge_requests/1
    * MotoyaLCedarを採用することにしたのでMRを閉じた
  * https://salsa.debian.org/fonts-team/fonts-motoya-l-cedar/-/merge_requests/1
    * motoya-l-cedar: udebを生成するようにフィードバックした
* 1/4
  * https://salsa.debian.org/installer-team/debian-installer/-/merge_requests/58
    * debian-installer: MotoyaLCedarのudebをインストールするようにフィードバックした
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1037256#85
    * MRの更新状況についてフィードバックした
  * https://kenhys.hatenablog.jp/entry/2025/01/04/223210
    * debian-installerの知見について記事を書いた
* 1/10
  * https://salsa.debian.org/installer-team/rootskel-gtk/-/merge_requests/5
    * rootskel-gtk: フォントの展開ロジックを追加した
  * https://salsa.debian.org/installer-team/debian-installer/-/merge_requests/59
    * debian-installer: フォントキャッシュを生成するようにフィードバックした
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1037256#90
    * debian-installer: MRに関してフィードバックした
* 1/13
  * https://kenhys.hatenablog.jp/entry/2025/01/13/172405
    * 6.11 linux-imageから既定で起動する方法を書いた
* 1/20
  * https://salsa.debian.org/installer-team/localechooser/-/merge_requests/9
    * localechooser: 日本語フォントを反映できるように処理を変更した
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1037256
  * https://people.debian.org/~kenhys/bug-1037256/index.html
    * d-iの修正に関する最新情報へと更新した
* 1/23
  * https://salsa.debian.org/installer-team/localechooser/-/merge_requests/9
    * localechooser: holgerさんの指摘に回答
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1037256#105
    * d-i: cyrilさんの指摘に回答しておいた
* 1/25
  * gr-framerowk: 0.73.12がリリースされていたので0.73.12+dfsgをアップロードした
* 1/27
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068202
    * bazel-bootstrapのnmuについてのコメントに回答
  * https://github.com/kenhys/sylpheed-htmlview/issues
    * staleなissueに対応した
  * https://github.com/deskflow/deskflow/pull/8142
    * deskflow: typoをlintianが見つけたのでフィードバックした
