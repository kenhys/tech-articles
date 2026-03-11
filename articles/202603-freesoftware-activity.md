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
