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
