---
title: "My Free Software Activities in November 2020"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

* fabre.debian.netを取得し、Aレコードを設定した
* debexpo https://salsa.debian.org/mentors.debian.net-team/debexpo/-/issues/125
  * ユーザーアカウント関連の記述がないのでフィードバックした。
* debexpo https://salsa.debian.org/mentors.debian.net-team/debexpo/-/merge_requests/165
  * サーバー起動時のポート番号があっていないのでフィードバックした。
* debexpo https://salsa.debian.org/mentors.debian.net-team/debexpo/-/merge_requests/167
  * パッケージがDebianにすでにあるのかどうかをPackage listから区別できるようにした
  * ↑のMRをどうすすめるべきか相談した
* https://kenhys.hatenablog.jp/entry/2020/11/08/151654
  * ↑のPRに関して、planet.d.o向け記事を書いた
* planet-team https://salsa.debian.org/planet-team/config
  * configにhackergotchiと呼ばれるfaceimageを設定した
* [http://rt.debian.org #8461]
  * やめたDDのdnsZoneEntryの取扱について消すか残すか分別しようとメールした
* lltsv_0.7.0-1
  * unstableへとアップロードした
* https://slide.rabbit-shocker.org/authors/kenhys/tokyodebian-debexpo-20201121/
  * Debian勉強会 12月の資料を作成した。
* libbenchmark-dev https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=968461
  * .aがシンボルをエクスポートしていない不具合について調べてみた。-fltoを-ffat-lto-objectsを適用するとたしかに良さそうであることを確認した。
* https://salsa.debian.org/science-team/benchmark/-/merge_requests/1
  * libbenchmarkでシンボルの問題を修正してMRを投げた。
