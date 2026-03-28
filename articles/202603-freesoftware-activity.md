---
title: "My Free Software Activities in March 2026"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 3月のハイライト

### 3月の活動記録

* 3/1
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1102789
    * rrdtool: メンテナーによって修正が去年の12月にはマージされたんだけど、一向に修正版がアップロードされる気配がない。1.9.0-2.1をnmuとしてdelayアップロードした。
  * https://salsa.debian.org/freexian-team/debusine/-/issues/1350
    * debusine: ppc64elでのビルドが他のworkerと比べて極端に遅い傾向があるのでフィードバック
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1127516
    * munin: libio-socket-inet6-perlがテスト実行時に不足していそうなのでフィードバック
* 3/2
  * https://salsa.debian.org/debian/mozc/-/merge_requests/19
    * mozc: libgwengui-qt5-devを使ってないので削除するフィードバック
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1114213
    * mozc: c++20に変更してFTBFSを修正するのがすでに適用されていることをフィードバック
* 3/11
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1127516
    * munin: FTBFSでこれに依存しているパッケージが削除されかねないので問題点を調査した
* 3/12
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1130483
    * libh3-dev: h3api.hが/usr/include/h3配下にインストールされない問題をかわりにフィードバックした
  * https://salsa.debian.org/postgresql/libh3/-/merge_requests/2
    * libh3: h3api.hが/usr/include/h3配下にインストールされるようにしてフィードバックした
* 3/20
  * https://github.com/fluent/fluentd-docker-image/pull/474
    * fluentd: trixie 13.4のポイントリリースがあったのでそれに追従
  * https://salsa.debian.org/debian/grow-your-ideas/-/issues
    * 解決済みのissueについて追記した
  * gr-framework: 0.73.24+dfsg-1をアップロードした
* 3/21
  * https://debianjp.connpass.com/event/385587/
    * debian勉強会に参加した
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1131426
    * python3-fontools: fonts-morisawa-bizudのFTBFSを調べていたら4.62.0以降にしれもらうかパッチ当ててもらわないといけないのでフィードバック
  * https://salsa.debian.org/fonts-team/fonts-morisawa-bizud-gothic/-/merge_requests/2
    * fonts-morisawa-bizud-gothic: format-14が重複しないようにするパッチをフィードバック
  * https://github.com/googlefonts/morisawa-biz-ud-gothic/pull/57
    * morisawa-biz-ud-gothic: build.pyの修正をupstreamにフィードバックした
  * https://github.com/googlefonts/morisawa-biz-ud-mincho/pull/54
    * morisawa-biz-ud-mincho: build.pyの修正をupstreamにフィードバックした
* 3/24
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1120909
    * budgie-desktop: python3-giがIMを壊したこともあるので、10.9が使い続けられる選択肢がほしいことをフィードバックした
* 3/25
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=967641
    * mozc: ubuntu側でGTK2依存が修正されたようなので、その情報をフィードバックした
  * https://salsa.debian.org/debian/mozc/-/merge_requests/20
    * mozc: ubuntu側の修正パッチをdebianでも適用するフィードバックをした
* 3/28
  * https://salsa.debian.org/debian/mozc/-/merge_requests/20
    * mozc: patch作者からフィードバックがあったので反映した
