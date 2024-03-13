---
title: "My Free Software Activities in March 2024"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

* 3/3
  * groonga-normalizer-mysql 1.2.3-2をアップロードした。libgroonga0t64に対応するため。
* 3/8
  * https://bugs.debian.org/1065647
    * lists.debian.orgのカテゴリ分けがわかりにくい気がするのでフィードバックした。
* 3/11
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1066031
    * groongaが依存するzeromq3のせいでBD-Uninstallableなのでgiven-backしてもらうようにフィードバックした。
* 3/12
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1066031#10
    * given-backは対象となる依存先のパッケージがInstalledな状態では実行できないっぽい。その場合はnmuとしてリクエストすべきなようだ。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1066519
    * givebackアクションをInstalledなパッケージに対して実行できないのでフィードバックしておいた。
