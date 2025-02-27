---
title: "My Free Software Activities in February 2025"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 2月のハイライト

### 2月の活動記録

* 2/3
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1094620
    * libhinawa: lintianの不具合で、gobject-introspection-binに依存させていたのを修正した
  * deskflow: v1.18.0のパッケージング作業 v1.19.0はいったん見送り。
* 2/5
  * https://github.com/rvm/rvm/pull/5544
    * rvm: Ruby 3.2.7がリリースされたのでフィードバック
* 2/8
  * gr-framework: gr-framework 0.73.12+dfsg-1だと既定のフォントを使おうとしてエラーがでることがわかったので修正した。
    - CMUSerif-Mathがないので、DejaVuSansをひとまず既定のフォントにして、pfbとかafmをシンボリックリンクで解決することにした。
      gr-framework 0.73.12+dfsg-2としてアップロードした。
* 2/9
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1092240
    * uim: gettext 0.23の環境だとFTBFSが発生するという問題の調査。EUC-JPなファイルが原因だったのでその旨をフィードバックした
    * https://x.com/kenhys/status/1888525742348354045 knokさんに対応を依頼しておいた
* 2/11
  * https://github.com/fluent/fluentd-docs-gitbook/pull/567
    * codespellを試してみた。cspellのほうがより厳しいが誤検出も多い印象。さっとチェックするならcodespellで十分かな
  * https://github.com/fluent/fluentd-docs-gitbook/pull/568
    * codespellをworkflowに組み込んで見ることにした
* 2/15
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1091303#15
    * ntpsec: armhfでビルドできない問題が解決していそうだったのでフィードバックした
  * https://github.com/rvm/rvm/pull/5549
    * rvm: 3.4.2がリリースされたのでフィードバックした
  * fabre.d.n: Ruby 3.4へと更新した
* 2/20
  * gr-framework: 0.73.13+dfsgのパッケージング作業。パッチの修正。
* 2/21
  * gr-framework: 0.73.13+dfsgのパッケージング作業。lintianのE:未解決のためアップロード断念。
* 2/22
  * gr-framework: 0.73.13+dfsgのフォントパッケージ分割とgrplotWidget.soの問題の修正。
* 2/23
  * dep5: https://salsa.debian.org/dep-team/deps/-/merge_requests/17
    * DEP-5でOFLをライセンスの例として明示することでフォントパッケージで誤ってSILとか指定しないようにフィードバックした
  * gr-framework: 0.73.13+dfsg-2をmigrationのためにアップロードした
* 2/25
  * groonga: 15.0.2+dfsg-1をアップロードした
