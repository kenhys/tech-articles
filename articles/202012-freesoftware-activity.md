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
* 12/6 https://mentors.debian.net/package/ngraph-gtk/#upload-1
  * ngraph-gtk 6.08.08-1 がスポンサー待ちだったのでビルドしてみたらテストがこけたのでフィードバックした。
* 12/7 https://mentors.debian.net/package/budgie-desktop-view/#upload-1
  * budgie-desktop-view 1.0.2-1のスポンサー待ちだったのでフィードバックした。
* 12/8 https://mentors.debian.net/package/ngraph-gtk/
  * ngraph-gtk 6.08.08-1 のスポンサーアップロードをした。
* 12/12 https://in2021.mini.debconf.org/contribute/cfp/
  * MiniDebConf India 2021のCfPを投げた
* 12/16 https://fabre.debian.net/bugs/show/977235
  * sentencepieceのFTBFSの修正をした
* 12/19 https://zenn.dev/kenhys/articles/20201219-lenovo-advent-calendar
  * "Debian: fabre.debian.netの開発の進め方と運用、得た学びの話" について記事を書いた
* 12/21 https://zenn.dev/kenhys/articles/20201221-lenovo-advent-calendar
  * "Debian: Debian: 在宅勤務するにあたりいまさらやったリモートでの起動・シャットダウンの設定をした話" について記事を書いた
* 12/22 https://github.com/collectd/collectd/pull/3795
  * collectdのluaプラグインをv6.0に対応させた(つもり)
* 12/24 budgie-desktop-view_1.1-1_source.changes
  * budgie-desktop-view_1.1-1のスポンサーアップロードをした。
* 12/25 groonga 10.1.0-1をunstableにアップロードした
* 12/27
  * https://mentors.debian.net/package/dnf/#upload-1
  * https://mentors.debian.net/package/libcomps/#upload-1
  * https://mentors.debian.net/package/libdnf/#upload-1
    * スポンサー探しているっぽいのでざっくりコメントした。ITPされていなかったっけ？
* 12/29
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=978068
    * digimend-dkmsをnew queueにアップロードした
* 12/30
  * https://mentors.debian.net/package/dnf/
  * https://mentors.debian.net/package/libdnf/
    * パッケージングに関してコメントしておいた
  * https://mentors.debian.net/package/ngraph-gtk/#upload-1
    * ngraph-gtkに関してコメントしておいた
* 12/31
  * ngraph-gtk_6.08.09-1のスポンサーアップロードをした
