---
title: "My Free Software Activities in October 2020"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

* Fluentd [Field type error! #3129](https://github.com/fluent/fluentd/issues/3129)
  * fluentd.confの設定が間違っているのを指摘した。
* Fluentd [Too many open files #3023](https://github.com/fluent/fluentd/issues/3023)
  * 既知のバグっぽいので1.11.2で修正されている旨をコメントした。
* [Q: When dnsZoneEntry is freed after DD retired](https://lists.debian.org/debian-project/2020/09/msg00027.html)
  * DDが退役したあともdnsZoneEntryが維持されているのでその件の問題提起をした。あとfabre.debian.netを再利用する交渉をした。
* lltsv [Specify background color explicitly for readability](https://github.com/sonots/lltsv/pull/29)
  * 背景色を明示することで黒背景でも視認しやすくするようにした。
* growl-for-linux [Fix some issues reported by lintian ](https://salsa.debian.org/debian/growl-for-linux/-/merge_requests/2)
  * マージした
* gntp-send: [Fix some issues reported by lintian](https://salsa.debian.org/debian/gntp-send/-/merge_requests/1)
  * マージした
* hal-flash [Fix some issues reported by lintian](https://salsa.debian.org/debian/hal-flash/-/merge_requests/1)
  * マージした
* sentencepiece
  * Fedoraで明示的にBuildRequires: python3-setuptoolsしないといけないので修正した
* sentencepiece
  * Debian: 0.1.93-1をアップロードした
* sentencepiece https://github.com/google/sentencepiece/issues/561
  * sentencepiece 0.1.93 fails to build on hppa を報告しておいた。
* sentencepiece https://github.com/google/sentencepiece/pull/562
  * cmake: use GNUInstallDirs.cmake on UNIX #562
* sentencepiece https://github.com/google/sentencepiece/pull/563
  * cmake: fix FTBFS on armel, mips, powerpc, m68k and sh4
* fonts-dejavu-core: https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=972431
  * piuparts fails by "FAIL: Package purging left files on system" 報告した。
* xfce4-weather-plugin https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=966668
  * fixed-upstream なのでフィードバックした
* fonts-dejavu-core: piuparts fails by "FAIL: Package purging left files on system" https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=972431
  * 重複していたので、forcemerge 897040 972431 した。
