---
title: "My Free Software Activities in October 2024"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 10月のハイライト

10月は技術書典17向けの原稿の改訂をしたのが主な活動。
ほかにもパッケージのメンテナンスだったり、deskflowをnew queueに放り込んだりした。

mozcを新しいリリースに追従させる件もすすめたいが、あれこれ考えることがあって
うまくすすんではいない。

### 10月の活動記録

* 10/4
  * https://bugs.debian.org/1081856
    * libaggのFTBFSがあがっていたので調査
* 10/5
  * https://kenhys.hatenablog.jp/entry/2024/10/05/170145
    * budgie desktopのウィンドウフォーカスの問題について書いた
  * https://github.com/BuddiesOfBudgie/budgie-desktop/issues/620
    * budgie desktopのウィンドウフォーカスの件についてフィードバックした
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1081856
    * agg: ftbfsに対するパッチを投げておいた
* 10/12
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1084988
    * deskflow: barrierのかわりにdeskflowをDebian sidに投入したいのでITPした
* 10/13
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1084988
    * deskflow: deskflowのパッケージング作業実施
    * https://github.com/jgm/pandoc/issues/9020 pandocでmanを生成させてみたら既知の問題を踏んだ。pandoc 3.1.7以降が必要らしい。
* 10/14
  * https://ftp-master.debian.org/new/deskflow_1.17.0+dfsg-1.html
    * deskflow: 1.17.0をnew queueにアップロードした
  * https://github.com/deskflow/deskflow/issues/7680
    * deskflow: helpメッセージがおかしいのでフィードバックした
  * https://github.com/deskflow/deskflow/pull/7682
    * deskflow: helpメッセージの.問題を修正してフィードバックした
  * https://salsa.debian.org/debian/libhinawa/-/merge_requests/7
    * libhinawa: MRのレビューをした
* 10/15
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1085173
    * mozc: 新しいリリースに追従するための調査とフィードバック
* 10/16
  * https://wiki.debian.org/Outreachy/December2024
    * outreachyの文言のフィードバック
* 10/29
  * https://techbookfest.org/product/5081155265101824
    * 技術書典17の原稿に関して審査にだした。
* 10/30
  * https://salsa.debian.org/debian/libhinawa/-/merge_requests/
    * libhinawa: MRのレビュー実施。
  * libhinawa: 4.0.2-3をアップロードした
  * gr-framework: 0.73.8+dfsg-1をアップロードした
  * https://mentors.debian.net/package/agg/#upload-1
    * agg: 2.7.0.r145+dfsg-1をレビューした
