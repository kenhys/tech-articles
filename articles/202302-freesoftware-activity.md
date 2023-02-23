---
title: "My Free Software Activities in Jan 2023"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

* 02/02
  * Groonga 12.1.2+dfsg-1をアップロードした
* 02/03
  * https://hosted.weblate.org/projects/debian-installer
    * d-iでもnon-freeソフトウェアじゃなくてファームウェアについての言及になっていたのを修正
  * https://www.debian.org/social_contract.1.1 翻訳旧版として移動
* 02/04
  * https://www.debian.org/social_contract 翻訳修正
* 02/09
  * https://www.debian.org/devel/website/ 翻訳修正
* 02/10
  * https://www.debian.org/devel/website/uptodate 翻訳修正
* 02/11
  * fabre.d.nでバグ一覧表示でFixmeを強調するタブ位置に修正
  * fabre.d.nでバグ一覧表示でパッケージ名を強調表示するように修正
* 02/12
  * https://www.debian.org/Bugs/index.ja.html の翻訳修正
* 02/13
  * https://www.debian.org/Bugs/Access.ja.html の翻訳修正
  * https://www.debian.org/Bugs/server-control.ja.html の翻訳修正
  * https://www.debian.org/Bugs/Developer.ja.html の翻訳修正
* 02/14
  * webwml/japanese/po/template.ja.po の翻訳修正
* 02/15
  * https://www.debian.org/distrib/netinst.ja.html の翻訳修正
  * https://www.debian.org/donations.ja.html の翻訳修正
* 02/16
  * https://github.com/BuddiesOfBudgie/budgie-desktop/issues/303
    * 通知の並び順についてフィードバック
* 02/20
  * https://www.debian.org/devel/debian-installer/
    * Debianイントーラーの翻訳修正
* 02/22
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1029821#29
    * gnome-initial-setupの既定値がanthyになっていて、そのままデフォルトでセットアップしてしまうと日本語入力できなくて詰む問題のパッチのフィードバック。
    * デフォルトをmozc-jpにすると日本語(Mozc)と表示されなくなる潜在的な問題があってその調査をした。初期化のタイミングでIBusエンジンの情報を取れないのが原因だった。
* 02/23
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1000064
    * Groongaがlibpcre3-devに依存していた問題を修正した
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1000012#10
    * nmapのPCRE2対応状況をフィードバック
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1000021#10
    * aircrack-ngのPCRE2対応状況をフィードバック
