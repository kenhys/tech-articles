---
title: "My Free Software Activities in Feb 2024"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

* 2/1
  * https://salsa.debian.org/debian/linux-firewire-utils
    * 権限をもらったのでdebian配下にプロジェクトを移転した
* 2/3
  * https://github.com/milter-manager/milter-manager/issues/206
    * milter-manager 2.2.7 for bookwormのパッケージをアップロードしておいた。
* 2/8
  * https://mentors.debian.net/package/libhitaki/#upload-3
    * libhitakiへのフィードバックを実施
  * https://github.com/groonga/groonga/discussions/1698
    * Groongaの64bit time_tに関してフィードバック。入力のtime_tは問題ありそうだけど、データベースにはあまり影響しなさそう。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1062131
    * groongaの64bit time_tに関してフィードバック。
* 2/9
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1062131
    * groonga 13.1.1+dfsg-1.2でabi=+time64を有効にしてexperimentalにアップロードした
  * https://mentors.debian.net/package/libhitaki
    * libhitakiをスポンサーしてnew queueにアップロードした(はず)
* 2/13
  * https://mentors.debian.net/package/libhitaki
    * アップロードに失敗していた、libhitakiのスポンサーアップロード。new queueに入った。
* 2/16
  * https://mentors.debian.net/package/libhitaki
    * libhitaki 0.2.1のスポンサーアップロード
* 2/18
  * https://salsa.debian.org/debian/hinawa-utils/-/issues/3
    * hinawa-utils 0.4.0をアップロードした。
* 2/20
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1056354
    * hinawa-utils 0.4.0-1により修正されているので、バグを閉じた。
* 2/23
  * https://github.com/collectd/collectd/pull/4238
    * luaプラグインでrelease-readyのチェックでひっかかっていた問題を修正した。
