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
* 1/14
  * https://kenhys.hatenablog.jp/entry/2024/01/14/171628
    * ConoHa VPS (v3)でDebianをインストールするための記事を書いた
    * https://zenn.dev/kenhys/articles/20240119-conoha-v3-debian にクロスポストしておいた。
* 1/17
  * https://github.com/collectd/collectd/pull/4238
    * Luaプラグインのテストがまったくない状態だったのでフィードバックした
* 1/18
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1061104
    * libxsimd-devをインストールしたときにいっしょにxtl-devがインストールされない問題をフィードバックした
  * https://salsa.debian.org/science-team/xsimd/-/merge_requests/4
    * libxsimd-devにフィードバックしておいた。
* 1/19
  * https://slide.rabbit-shocker.org/authors/kenhys/tokyodebian-conoha-v3-debian-202401/
    * Debian勉強会の資料を公開した
* 1/20
  * https://slide.rabbit-shocker.org/authors/kenhys/tokyodebian-conoha-v3-debian-202401/
    * Debian勉強会にてConoHa v3へのインストール方法について紹介した。
  * https://salsa.debian.org/debian/libhinawa/-/issues/28
    * libhinawa 4.0.1-1をアップロードした。アップストリームに修正がとりこまれたのでパッチが不要になった。
  * Groonga 13.1.1+dsfg-1をunstableへとアップロードした。
* 1/21
  * https://github.com/collectd/collectd/pull/4238
    * collectdのLuaプラグインにテストを追加するPRのフィードバックへの対応
* 1/27
  * https://salsa.debian.org/debian/hinawa-utils/-/issues/3
    * hinawa-utilsの今後についてのフィードバック
  * https://github.com/collectd/collectd/pull/3227
    * collectd postgresqlのPRをmainに追従した
* 1/30
  * https://salsa.debian.org/debian/libhitaki
    * 権限をもらったのでlibhitakiをdebian/配下にtransferした
