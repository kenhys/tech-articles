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
  * http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1071048
    * rust-coreutilsのarmhfでのFTBFSをフィードバックした
* 5/14
  * https://github.com/epics-base/epics-base/issues/483
    * epics-baseのヘッダのイントールパスの変更を提案しておいた
* 5/17
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068186
    * mozcがftbfsになる問題のフィードバックをした
    * upstreamのパッチをフィードバックした
    * パッチを適用してもそれですべて修正できるわけではないということがわかったのでコメントしておいた
* 5/18
  * https://github.com/epics-base/epics-base/issues/483
    * epics-baseに対してデフォルトパスを変更するように提案したが、そもそもシステムワイドでインストールすべきではないことがわかった。
      複数のバージョンをインストールすることを想定していて、その場合は明示的にINSTALL_LOCATIONを独自のものにする流儀のようだ。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068186#28
    * MozcがsidでFTBFSとなる問題の追加パッチを作成した
* 5/19
  * https://salsa.debian.org/salsa-ci-team/pipeline/-/merge_requests/505
    * gbp export-origが失敗しても処理続けちゃうのはまずいのでfallbackを無効化できるようにフィードバックした
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1045435
    * mozc のdouble buildの問題を修正するパッチを投げた
* 5/22
  * https://twitter.com/kenhys/status/1793132755821416680
    * Mozcのメンテナーであるいわまつさんにパッチをみてもらうように依頼
  * https://salsa.debian.org/salsa-ci-team/pipeline/-/merge_requests/505
    * MRのCONTRIBUTORSへの記載が漏れていたので更新
* 5/24
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1049806
    * Mozc: #1045434で再現しなかったので、unreproducibleタグを付与しておいた
* 5/25
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1071827
    * mozc: gbp buildpackageがpristine-tar branchのコミットがないせいでできないのでフィードバックした
  * https://salsa.debian.org/science-team/epics-base/-/merge_requests/2
    * epics-base: epics-base.pcのパスを修正するパッチを投げたが、MRとしてもフィードバックした
  * https://salsa.debian.org/science-team/epics-base/-/merge_requests/3
    * epics-base: epics-base.pcのincludeパスを修正するパッチを投げたが、MRとしてもフィードバックした
  * https://salsa.debian.org/science-team/epics-base/-/merge_requests/4
    * epics-base: gbp.confのcompressionの設定が誤っているのでフィードバックした
* 5/26
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1066031
    * zeromq3: auto rebuildで依存関係の問題が解決しているのでバグを閉じた。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068186
    * mozc: twitterはもうみていないかもしれないので、メンテナーのiwamatsuさんに直接メール @debian.org してコンタクトを試みた
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1071949
    * freerdp3: armhfのFTBFSをフィードバックした
