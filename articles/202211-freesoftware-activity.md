---
title: "My Free Software Activities in Nov 2022"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

* 11/08
  * Grooga 12.0.4-1.1がsalsaに反映されていないため適用しておいた
* 11/09 https://github.com/clear-code/fx-meta-installer/pull/21
  * ショートカットのフォールバックが古いままだったのを修正
* 11/12
  * Groonga 12.0.9とgroonga-normalizer-mysql 1.1.9をアップロード
* 11/13
  * Debian勉強会の資料作成
* 11/14
  * libhinawa 2.5.1のアップロード。dput-ngに切り替えて試してみた。
* 11/15
  * fcitx-imlist 0.5.1-7をアップロード。
  * gntp-send 0.3.4-7をアップロード。
* 11/17
  * growl-for-linux 0.8.5-9をアップロード。
* 11/18
  * fasttext 0.9.2-4をアップロード。
  * fcitx-imlist 0.5.1-8をアップロード。
  * Debian勉強会の資料を修正、アップロード。
* 11/19
  * groonga_12.0.9+dfsg2-1をアップロード。
  * 11月Debian勉強会で発表した。
  * groonga_12.0.9+dfsg2-2をアップロード。hurd-i386に対応した。
  * lltsv_0.7.0-2をアップロードした。
* 11/20
  * hinawa-utils 0.3.0-2をアップロードした。
* 11/21
  * groonga-normalizer-mysql 1.1.9-2をアップロード。
  * porterbox DNSのメンテナンスに関して@jwilkさんに相談メール
  * sentencepiece 0.1.97-3をアップロード。同一バージョン再リリースされていた問題に対処したつもり。
* 11/22
  * https://github.com/google/sentencepiece/issues/794
    * パッチを抱えるのはしんどいので、新しいバージョンをリリースしなおしてくれないかとフィードバックしてみた。
      * 実際のところはpre-releaseラベルつけてリリースしていた様子なので、早合点してパッケージしたのがよろしくなかった。
* 11/23
  * https://salsa.debian.org/kenhys/qa/-/tree/github_releases
    * pre-releaseなラベルを無視する方法を実装してみた。しかし、assetsと自動的に生成されるtarball_urlが違うのでd/watchでその違いは吸収しないといけない。
