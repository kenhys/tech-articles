---
title: "My Free Software Activities in Dec 2023"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

* 12/07
  * https://mentors.debian.net/package/xnvme/#upload-10
    * xnvmeパッケージへフィードバックした
* 12/09
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1057748
    * digimend-dkms 11-4をexperimentalにアップロードした
  * developer reference 7.5.1の翻訳更新した
* 12/13
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1058535
    * FTBFSの追試。gi-docgenがバージョンを正しくパースできていなくてエラーになっていた。
* 12/14
  * https://salsa.debian.org/debian/digimend-dkms
    * digimend-dkms 11-5をunstableにアップロードした
* 12/15
  * https://mentors.debian.net/package/libhinoko/
    * libhinoko 1.0.1-1をスポンサーアップロードした
* 12/21
  * https://github.com/collectd/collectd/pull/3840
    * collectdに以前投げたパッチに関してフィードバック そういえばbullseyeに間に合うように入れたんだった。
* 12/23
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1059350
    * debian-keyringが更新されていないのでフィードバック。debianのインフラではsalsa.d.oと同期しているから問題ないらしい。
  * https://salsa.debian.org/debian/digimend-dkms
    * digimend-dkms 11-7をunstableにアップロードした。loong64をビルド対象に追加した。
* 12/24
  * https://github.com/collectd/collectd/pull/3778
    * LuaJITを検出するためのPRを更新した。3年ほど前のパッチだ。
* 12/26
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1052037
    * fasttext: armelでインポートできない問題、他の人が直したはずが修正されてなかったので対応した。
* 12/28
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1052037
    * fasttext: armelでインポートできない問題、こんどこそちゃんと修正したはず。0.9.2+ds-7をアップロードした。
* 12/30
  * https://github.com/collectd/collectd/pull/3795
    * collectdのLuaプラグインをv6 APIへ移植するPRを書き直した。以前のコードはちょっと読みにくいのでかなりよくなった気がする。再現用の手順もフィードバックしたので検証しやすいはず。
  * https://github.com/collectd/collectd/pull/3777
  * https://github.com/collectd/collectd/pull/3779
    * 既存のLuaプラグインのパッチを更新してmainに追従した。
* 12/31
  * https://github.com/collectd/collectd/pull/3795
    * Luaのv6対応の指摘事項を修正した。
