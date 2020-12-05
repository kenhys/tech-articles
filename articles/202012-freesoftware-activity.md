---
title: "My Free Software Activities in December 2020"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

* 12/5 collectd https://github.com/collectd/collectd/pull/3784
  * cirrusでCentOS6でのテストをやめるようにPRを投げた。こいつはテストを失敗させる原因にもなっていた。
* 12/5 collectd https://github.com/collectd/collectd/pull/3785
  * Travis-CIに依存しているけど、遅いのでGitHub Actionsに移行するようなPRを投げてみた。
* 12/5 libhal1-flash https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=972870
  * すでにQA扱いだし、RM: libhal1-flash -- RoQA; No longer maintained and replaced by HTML5(DRM)の削除リクエストに変更した。
