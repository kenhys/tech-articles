---
title: "My Free Software Activities in March 2025"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 3月のハイライト

### 3月の活動記録

* 3/1
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1099191
    * d-i: インストーラーでミラーを選択したときにしばらく刺さる問題についてフィードバックした
* 3/2
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1099191
    * d-i: choose-mirrorでミラー選択時に20-30分ほど刺さるケースがあるところまでログ収集した
* 3/5
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1099191
    * d-i: choose-mirrorやdebian-installer-utilsの挙動を調査した
* 3/6
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1099191
    * d-i: choose-mirrorのエッジケースの挙動についてフィードバックした。
  * libfreeaptx: 0.2.2がリリースされていたので、アップロードしておいた
* 3/7
  * groonga-normalizer-mysql: 1.2.5がリリースされていたのでアップロードした
* 3/10
  * mozc: abseil 20240722.0がunstableに投入され、FTBFSが発生していたので mozc 2.29.5160.102+dfsg-1.4で修正した
* 3/11
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1099292
    * t-codeのFTBFSにフィードバックした
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1050554
    * budgie-desktop: タスクバーが反応しない問題最近再現していないので閉じた
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1100078
    * budgie-desktop: ログインで失敗する問題がVirtualboxでも再現したのでフィードバック
    * 再現条件がある程度限定されたっぽいのでログをフィードバック
* 3/12
  * https://github.com/fluent/fluentd-kubernetes-daemonset/pull/1571
    * fluentd-k8s-daemonset: CVE-2025-27788の問題のためにフィードバック
  * https://github.com/fluent/fluentd-kubernetes-daemonset/pull/1572
    * fluentd-k8s-daemonset: dependabotのscan rule古すぎたので更新
  * groonga: 15.0.3+dsfgをアップロードした
* 3/16
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1100078
    * budgie-desktop: 10.9.2-8でログイン時にクラッシュする問題が解決したのでフィードバック
  * friso: 1.6.4+ds-3をアップロードしておいた
  * fcitx-dbus-status: 2016062301-5をアップロードしておいた
* 3/17
  * deskflow: deskflow 1.18.0がunstableに入ったので、v1.20.1をアップロードしておいた
  * https://github.com/deskflow/deskflow/pull/8373
    * deskflow: パッケージングしていたときに気づいたtypoをフィードバックした
