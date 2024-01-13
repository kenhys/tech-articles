---
title: "My Free Software Activities in Jan 2024"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

* 1/1
  * https://github.com/collectd/collectd/pull/3795
    * v6への移植に関する指摘事項を反映した。これでv6対応はそろそろマージされていいはず。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1059075
    * lltsvのloong64に関する要望だが #1059025 と重複しているので閉じた。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1059025
    * lltsvのloong64サポートはそもそもgolang-1.21がloong64サポートしていないのでそっちを解決するのが先。block 1059025 by 1055087
* 1/7
  * https://github.com/collectd/collectd/pull/3779
    * luaプラグインにコールバックを追加する実装の修正。notificationは別PRに分けることにした。
* 1/9
  * https://lists.debian.org/debian-security-tracker/2024/01/msg00009.html
    * CVEのbullseyeの表示で違和感があったのでフィードバックした。
* 1/11
  * bibata-cursor-theme 2.0.5-1をアップロードした
* 1/13
  * https://github.com/collectd/collectd/pull/3795
    * collectd v6.0対応のLuaに関するドキュメントを追加した。
  * https://github.com/collectd/collectd/pull/4235
    * collectdのnotificationの追加実装をした。
  * CollectdのTrusted Contributorsにoctoさんから招待された。このTrusted Contributorsというのはコードレビュー担当扱いらしい。Lablesとかを設定できる権限がある。
