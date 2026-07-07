---
title: "My Free Software Activities in July 2026"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 7月のハイライト

### 7月の活動記録

* 7/4
  * mozc: bazel-bootstrap 7.xが投入されたのでMozcのビルドをどうにかできないか調査開始
* 7/5
  * mozc: mozc 2.31.5712.102だとBazel 8.0.0をサポート開始しはじめなので対処しやすいかと思ったが、Mozcが対象とするlibabslが古いのでパッチあてて対処等しんどそう。3.33.6133をターゲットにしてみようと四苦八苦した。オフラインでビルドするのは茨の道であることを痛感した。
* 7/7
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=869642
    * devscripts: 2.26.10で複数の.dscにdebsign --re-signしたときに"Successfully signed dsc, dsc, dsc files"みたいに繰り返される不具合が修正されたことを教えてもらったのでフィードバック。

