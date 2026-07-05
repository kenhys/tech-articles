---
title: "My Free Software Activities in June 2026"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 6月のハイライト

6月はdebian-mirror.sakura.ne.jp停止するのでmirror teamにフィードバックしたのが
印象に残っている。数日くらいでpingはご法度。なお、結果としてはdebian-mirror.sakura.jpが
ftp.jp.debian.orgから削除されただけじゃなくて、ftp.jp.debian.orgとdeb.debian.orgが一緒になった。
他のミラーの状況がよろしくなかったらしいのであわせて整理されたようだ。
deb.debian.orgが不調だからといって、ftp.jp.debian.orgを指定する意味はもうなくなった。
（以前、debian-installerをWiFiブリッジで起動したときに疎通できなくなる問題を踏んだとき、ftp.jp.debian.org
を指定すると回避できたりしたけど、その手法は使えなくなったことになる）

### 6月の活動記録

* 6/1
  * https://github.com/deskflow/deskflow/pull/9812
    * deskflow: ftbfs with OpenSSL 4.0.0のパッチをフィードバックした
  * https://github.com/deskflow/deskflow/pull/9813
    * deskflow: ciでarm64のジョブが失敗しがちなのをフィードバックした
* 6/2
  * https://salsa.debian.org/mirror-team/masterlist/-/merge_requests/18
    * debian-mirror.sakura.ne.jpが停止するのでフィードバック
* 6/3
  * https://lists.debian.org/debian-www/2026/06/msg00001.html
    * www-masterのtrixie移行にともなうkccの必要性についてフィードバック
* 6/5
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1138281
    * hwatch: 0.4.2-2をスポンサーアップロードした
* 6/13
  * https://gitlab.com/clear-code/cc-20th-anniversary-timeline/-/merge_requests/12
    * 年表アプリでGitHubとかGitLabのissue commentを同期できるようにするフィードバック
* 6/20
  * gr-framework: 0.73.26+dfsg-1をアップロードした
