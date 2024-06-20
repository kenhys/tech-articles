---
title: "My Free Software Activities in June 2024"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

* 6/1
  * https://salsa.debian.org/debian/mozc/-/merge_requests/11
    * mozc: source after successful buildのパッチをマージリクエストにしてフィードバックしておいた
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1049806
    * mozc: binary after successful buildが再現したのでunreproducibleタグを除去した
  * https://salsa.debian.org/debian/mozc/-/merge_requests/12
    * mozc: blhcはmozcのビルドでまだ満たせないのでallow_failure: trueを適用するようにフィードバック
  * https://salsa.debian.org/vim-team/vim-debian/-/merge_requests/16
    * deb822でEnabled:フィールドのシンタックスハイライトができないのを修正した。フィードバック先のリポジトリはここでいいんだろうか。vim-runtimeに含まれるはずのものなんだけど。
* 6/2
  * https://github.com/vim/vim/pull/14898
    * vim: deb822のEnabledフィールドへのフィードバックをvim本体にもPRとして投げておいた。
  * https://kenhys.hatenablog.jp/entry/2024/01/14/171628
    * ConoHa VPS V3でDebianをインストールするのに、標準テンプレートとして提供されるようになったので、注記を追記しておいた。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068202#12
    * bazel-bootstrap: abslが多分更新されたせいでFTBFSが発生していたのでパッチを投げた
* 6/3
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068202#19
  * https://salsa.debian.org/bazel-team/bazel-bootstrap/-/merge_requests/3
    * bazel-bootstrap: パッチをMRとしてフィードバックしておいた
* 6/4
  * https://salsa.debian.org/bazel-team/bazel-bootstrap/-/merge_requests/3
    * bazel-bootstrap: テストが失敗するとの指摘に対して、piupartsだと現状のパッケージでは必ず失敗する旨をフィードバックした
* 6/5
  * https://salsa.debian.org/salsa-ci-team/pipeline/-/merge_requests/505
    * フィードバックがあったのでmozcのforkリポジトリで実験
* 6/9
  * https://salsa.debian.org/debian/mozc/-/merge_requests/14
    * mozc: debian/watchを追加するフィードバック
* 6/14
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1073192
    * lz4: CMake向けのファイルがインストールされない問題をフィードバック
* 6/17
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1073192
    * lz4: CMakeでビルドするためのパッチをフィードバック
* 6/20
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1070063
    * remmina: https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1070078 で修正されていそうなのでフィードバックした
