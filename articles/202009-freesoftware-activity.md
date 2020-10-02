---
title: "フリーソフトウェア関連活動記録 2020/09"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

* [mmdebstrap: failed to execute qemu-xxx-static with --mode=proot](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=970789)
  * `--mode=proot` で実行できないバグがあるので、パッチをつけてフィードバックした。
* [popularity-contest: a way to exclude certain packages](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=632438)
  * popularity-contestで特定のパッケージを除外できるようにするべきかどうかの議論に参加した。
* [Use correct SPDX license identifier](https://github.com/rubyzip/rubyzip/pull/458)
  * BSD-2-Clauseが正しいというのでフィードバックした。
* [build with lua-cjson 2.1.0-1 fails for luajit 2.1](https://github.com/JakobGreen/lua-requests/issues/24)
  * luajitだとビルドできない問題は、lua-requestsがlua-cjson 2.1.0.6-1に依存すれば解決するはずなのでコメントした。
* debian: fasttext 0.9.2-3 をアップロード
  * hurdでFTBFSを修正。DEB_BUILD_GNU_TYPEを使うようにすることで.soが見つからない問題を解決した。
* debian: sentencepiece 0.1.92-2 をアップロード
  * hurdでFTBFSを修正。DEB_BUILD_GNU_TYPEを使うようにすることで.soが見つからない問題を解決した。
  * m68k,powerpc,sh4向けに-latomicを追加するパッチを更新した。
* [Please move(transfer) debian/fasttext, debian/sentencepiece into Debian Science Team](https://salsa.debian.org/salsa/support/-/issues/235)
  * fasttext,sentencepieceのリポジトリをDebian Science Teamに移動するようにリクエストした。
