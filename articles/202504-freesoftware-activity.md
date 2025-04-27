---
title: "My Free Software Activities in April 2025"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 4月のハイライト

4h月は、Debian Trixieにむけたマイルストーン2のフリーズ期間に突入した。
先月はツールチェインだったが、今月からは一般のパッケージにもフリーズの制限がかかる。

groongaやdeskflowのパッケージの更新をした。

deskflowはソフトフリーズ直前で1.21.2がでてしまったが、unblockして投入すべきほどの修正ではなさそうなため見送った。

gr-frameworkも0.73.14がフリーズ後にリリースされたが、unblockして投入するほどの修正かは判断が難しく見送った。

rvmについてはリリースされてからすぐに対応してフィードバックしたので嬉しかった人はいたんじゃないかと思う。

他は、FTBFSな問題について他のパッケージにフィードバックをしたくらいか。最近同僚に触発されてrubocopを覚えたので積極的に試してみている。

### 4月の活動記録

* 4/2
  * groonga: 15.0.4+dfsgをDebian unstableへとアップロードしておいた
  * deskflow: 1.21.1+dfsgをDebian unstableへとアップロードしておいた
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1091303#41
    * ntpsec: armhfで以前としてFTBFSが発生しているようなのでパッチを投げておいた
* 4/10
  * rvm: https://github.com/rvm/rvm/pull/5560 
* 4/15
  * rvm: https://github.com/rvm/rvm/pull/5562
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1102328
    * bibata-cursor-theme: unreproducibleなため閉じた
* 4/26
  * https://github.com/milter-manager/milter-manager/issues/210
    * milter-manager: armhfでビルドできなくなっているのでフィードバック
  * https://github.com/fluent/fluentd/pull/4928
    * fluentd: rubocopを使ってTrailinWhitespaceの警告を減らすためのフィードバック
  * https://github.com/fluent/fluentd/pull/4929
  * https://github.com/fluent/fluentd/pull/4930
    * fluentd: rubocopでPerformance/StringIdentifierArgumentの警告を改善するためのフィードバック
  * https://github.com/fluent/fluentd/pull/4931
    * fluentd: rubocopでPerformance/CollectionLiteralInLoopの警告を改善するためのフィードバック
  * https://github.com/tagomoris/fluentd-v1-checker/pull/1
    * fluentd-v1-checker: ruby 2.6までしか開発環境でインストールできないのでフィードバック
* 4/27
  * https://github.com/fluent/fluentd/pull/4932
    * fluentd: rubocopでPerformance/StringIdentifierArgumentの警告を改善するためのフィードバック
  * https://github.com/fluent/fluentd/pull/4933
    * fluentd: rubocopでStringIncludeの警告を改善するためのフィードバック
  * https://github.com/fluent/fluentd/pull/4934
    * fluentd: rubocopでConstantRegexpの警告を改善するためのフィードバック
  * https://github.com/fluent/fluentd/pull/4935
    * fluentd: rubocopでRedundantBlockCallの警告を改善するためのフィードバック
