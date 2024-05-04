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
