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
* 7/11
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1085173
    * mozc: debuildでローカルビルドにはじめて成功する。https://x.com/kenhys/status/2075898456506581243 にて成果のショート動画をあげてみた。
* 7/12
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1085173
    * mozc: debuildによるローカルビルドには成功したが、gbp buildpackageによるクリーンビルドに失敗した問題の修正を行った。gbp buildpackageでビルドできるようになったので、手元のコミットを整理とかもろもろしたら、experimentalにパッケージをあげて検証してもらうフェーズにはいれるかもしれない。
* 7/14
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1085173
    * mozc: zip codeのパッチを追加して、郵便番号から変換できるようにした。
* 7/16
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1085173
    * mozc: debhelper 14にあげようとしたらビルドに失敗するようになった。sbuildでのみ判明したビルドエラー等も修正。
* 7/17
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1085173
    * mozc: hardening対応とuim-mozcが動作しなかった問題の修正をした。
* 7/18
  * https://salsa.debian.org/debian/groonga/-/merge_requests/6
    * groonga: systemd-sysusersやsystemd-tmpfilesに以降するMRをレビューした
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1142148
    * groonga: bloscが32bitサポートしていないため削除した。また16.0.8+dfsg-1としてアップロードした。
* 7/22
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1085173
    * mozc: 3.33.6133+ds1-0.1~exp1をexperimentalにアップロードした
* 7/24
  * https://lists.debian.org/debian-input-method/2026/07/msg00099.html
    * debian-input-method: MLでanthyの今後について質問した
* 7/31
  * https://github.com/fujimotok/honkit-plugin-breadcrumbs/pull/1
    * honkit-plugin-breadcrumbsのseparator指定が効かない不具合を修正した
