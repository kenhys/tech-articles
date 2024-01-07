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
