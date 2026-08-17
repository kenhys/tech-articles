---
title: "My Free Software Activities in August 2026"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 8月のハイライト

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
