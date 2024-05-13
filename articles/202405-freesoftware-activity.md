---
title: "My Free Software Activities in May 2024"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

* 5/3
  * lintianのメンテナンスが滞っているようなのでsalsaのlintianチームにjoin requestしてみた。
  * https://salsa.debian.org/lintian/lintian/-/merge_requests/446
    * CONTRIBUTING.mdをrebaseしようとしてもできなかったので、reporterにrebaseするように依頼。既存のMRはどうもrebaseしようとしてもupstreamメンバーによるrebaseを明示的に許可していなさそうなので、最新に追従するということができない。
* 5/4
  * ディストリビューション開発もくもく会に参加した
  * https://tracker.debian.org/pkg/digimend-dkms
    * digimend-dkms 13-1をunstableにアップロードした
  * https://github.com/DIGImend/digimend-kernel-drivers/pull/324
    * digimend-dkmsをDebianでメンテナンスしているのでそのことをフィードバックした
  * https://github.com/DIGImend/digimend-kernel-drivers/pull/686
    * digimend-dkmsのskip-without-CONFIG_USB_HID.patchをupstreamにフィードバックした
  * https://github.com/DIGImend/digimend-kernel-drivers/pull/687
    * digimend-dkmsのudev-udevdir.patchをupstreamにフィードバックした
  * https://tracker.debian.org/pkg/libhinawa
    * libhinawa 4.0.2-1をunstableにアップロードした
  * https://github.com/collectd/collectd/pull/3227
    * collectdへpostgresqlのmetadata拡張をrebaseしておいた。mainにマージしたい
  * https://salsa.debian.org/debian/libhinawa/-/issues/29
    * libhinawa 4.0.2-1をアップロードしたのでissuesを閉じた
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1059706
    * collectdのPRをみていたら、CIが壊れているのでepics-base.pcが壊れている理由について調べてフィードバックした。
    * epics-base.pcが壊れている問題を調査して、暫定パッチをフィードバックしておいた。
* 5/5
  * https://salsa.debian.org/kenhys/lintian/-/merge_requests/1
    * autopkgtestが1h超えるので、タイムアウトの指定値をチェックするようにしてみた
  * https://salsa.debian.org/lintian/lintian/-/merge_requests/503
    * autopkgtestが1h超えるので、タイムアウトの指定値をチェックするようにしてみた
  * https://lists.debian.org/debian-www/2024/05/msg00013.html
    * lists.debian.orgのカテゴリ分けの提案の話がすすんでいないので再度投稿しておいた
* 5/13
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1071044
    * rust-libmimalloc-sysのarmhfでのFTBFSをフィードバックした
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1071046
    * rust-mimallocのarmhfでのFTBFSをフィードバックした
