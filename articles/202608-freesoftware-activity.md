---
title: "My Free Software Activities in August 2026"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 8月のハイライト

8月はDebianのMozcをいかにより新しいバージョンに更新していくかについての発表をDebian勉強会で実施した。
uim-mozcの問題が解決しなかったら、uim-mozcを廃止しようかと考えていたが、幸い修正できたので少なくとも
forkyでは維持していきたい。Bazel移行ができたら次の3.34にあげられるのかどうかを検証してみたい。

DebianのLLMに関するGRは結論を急ぎすぎて分断を発生させてしまった気がしないでもない。

### 8月の活動記録

* 8/1
  * sentencepiece: 0.2.2がリリースされていることに気づいたので更新作業中。pybindに変わっているのでそのあたりに追従。パッチもそのままではあたらない。
* 8/2
  * sentencepiece: pythonモジュールが使えなくなっていたのでその対応作業。autopkgtestも失敗するためテストケースを修正。0.2.2-1としてアップロードした。
* 8/4
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1143520
    * groonga: apache-arrowの影響でFTBFSになっていたのを修正して16.0.8+dfsg-2をアップロードした
* 8/8
  * debian勉強会向けの資料作成作業実施
* 8/13
  * https://salsa.debian.org/debian/groonga/-/merge_requests/6
    * groonga: sysusersを使うMRをとりこんだ
  * groonga: 16.0.9+dfsg-1をアップロードした
* 8/16
  * mozc: zip codeパッチを更新してmozc_3.33.6133+ds1-0.1~exp2をアップロード
* 8/17
  * libsocket-perl: CVE-2026-12087に関してパッチをバックポートしたりメーリングリストにフィードバックした
* 8/20
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1144753
    * fcitx-dbus-status: fcitx 4.x削除の動きをうけて、RMリクエストを投げておいた
    * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1144892
* 8/22
  * https://github.com/kenhys/fcitx-imlist/releases/tag/0.6.0
    * fcitx-imlist: Fcitx 5.xをサポートした0.6.0をリリース
  * https://www.debian.org/vote/2026/vote_002
    * LLMに関するGRに投票した
  * https://slide.rabbit-shocker.org/authors/kenhys/tokyodebian-update-mozc-202608/
    * Debian勉強会で 「(帰ってきた)より新しいMozcをDebianでも使いたい」について発表
* 8/24
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1145132
    * groonga: llama向けのパッチが不要になったので削除してアップロードした
* 8/26
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1145169
    * deskflow: 脆弱性対策で1.26.0+dfsg-4をアップロードした。changelogのCVEの記述を間違えた。
* 8/27
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1145779
    * budgie-core: rc.xmlの記述エラーが表示されるのでフィードバックした
  * https://github.com/deskflow/deskflow/security/advisories/GHSA-xpjj-c4qw-mv8q
    * deskflow: CVE-2026-41476に関連してフィードバックした
* 8/28
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1085173
    * mozc: uim-mozcの問題を修正した
* 8/29
  * https://github.com/e-kato/macuim/pull/12
    * macuim: debian向けのuim-mozcパッチの修正をフィードバックした
* 8/30
  * deskflow: CVE-2026-41476のパッチを更新して1.26.0+dfsg-5としてアップロードした
