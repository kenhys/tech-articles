---
title: "My Free Software Activities in July 2024"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 8月のハイライト

8月はGR frameworkというものをパッケージングしてみた。(自分は使う予定はないのだけれども要望があったので)
それに関連して、GNU Radioの表記がぶれていたのでフィードバックしたりもしました。

あとは技技技術書典17にオンライン参加することを決めました。
既刊の改訂版をだそうかと考えています。

### 8月の活動記録

* 8/3
  * https://lists.debian.org/debian-devel/2024/08/msg00000.html
    * DEP-18のコラボレーションに関する私見をまとめて投稿しておいた。個人でメンテナンスしているやつのポリシーが明確化されているとこっちも動きやすい
* 8/5
  * https://salsa.debian.org/debian/mozc/-/merge_requests/12
    * mozc: pipelineが常に失敗するのでマージした
  * https://salsa.debian.org/debian/mozc/-/merge_requests/11
    * mozc: MR!12をマージしたのでdebian/sidに追従した
  * https://salsa.debian.org/debian/mozc/-/merge_requests/14
    * mozc: MR!12をマージしたのでdebian/sidに追従した
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1077974
    * gr-framework: ITPによりパッケージングする意図を宣言した
* 8/6
  * https://salsa.debian.org/bottoms/pkg-gr-air-modes/-/merge_requests/3
    * gr-air-modes: GNU Radioの表記に統一
  * https://salsa.debian.org/rubund/gr-dab/-/merge_requests/2
    * gr-dab: GNU Radioの表記に統一
  * https://salsa.debian.org/bottoms/pkg-gr-fosphor/-/merge_requests/1
    * gr-fosphor: GNU Radioの表記に統一
  * https://salsa.debian.org/debian-hamradio-team/gr-gsm/-/merge_requests/2
    * gr-gsm: GNU Radioの表記に統一
  * https://salsa.debian.org/debian-hamradio-team/gr-hpsdr/-/merge_requests/3
    * gr-hpsdr: GNU Radioの表記に統一
  * https://salsa.debian.org/bottoms/pkg-gr-osmosdr/-/merge_requests/1
    * gr-osmosdr: GNU Radioの表記に統一
  * https://salsa.debian.org/debian-hamradio-team/gr-limesdr/-/merge_requests/2
    * gr-limesdr: GNU Radioの表記に統一
* 8/8
  * https://salsa.debian.org/debian/lz4/-/merge_requests/9
    * lz4: depends libxxhash-devするようにフィードバック
* 8/9
  * https://salsa.debian.org/debian/lz4/-/merge_requests/9
    * lz4: libxxhashが透過的にインストールされないと失敗する件、yuzuで事前にインストールされていれば解決するのでフィードバック
* 8/10
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1078280
    * docker.io: docker composeの件をフィードバックしようとしたら、FTBFSで引っかかったのでエラーについて報告
  * https://salsa.debian.org/bottoms/pkg-gr-air-modes/-/merge_requests/3
  * https://salsa.debian.org/rubund/gr-dab/-/merge_requests/2
  * https://salsa.debian.org/bottoms/pkg-gr-fosphor/-/merge_requests/1
  * https://salsa.debian.org/debian-hamradio-team/gr-gsm/-/merge_requests/2
  * https://salsa.debian.org/debian-hamradio-team/gr-hpsdr/-/merge_requests/3
  * https://salsa.debian.org/bottoms/pkg-gr-osmosdr/-/merge_requests/1
  * https://salsa.debian.org/debian-hamradio-team/gr-limesdr/-/merge_requests/2
    * 直近のメンテナーにレビューを依頼した
* 8/12
  * https://github.com/sciapp/gr/pull/187
    * gr-frameworkをパッケージングしようとしていて見つけたtypoをフィードバックした
* 8/17
  * https://salsa.debian.org/science-team/gr-framework/
    * ようやく作業中のgr-frameworkのリポジトリをsalsa.d.oに反映した
  * https://lists.debian.org/debian-science/2024/08/threads.html
    * gr-frameworkのCI/CD設定を変更してもらうように依頼を投げた
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1053061
    * mecabのFTBFSについてはDebian勉強会でknokさんにお願いしておいた
* 8/18
  * https://ftp-master.debian.org/new/gr-framework_0.73.7+dfsg-1.html
    * gr-framework: new-queueにパッケージをアップロードするところまで実施した
  * https://github.com/sciapp/gr/pull/188
    * gr-framework: gksmがcmakeを使うとインストールされない問題をフィードバックした
* 8/19
  * https://github.com/collectd/collectd/pull/4298
    * epics-base: collectdのCIで失敗していた問題がunstableで解決しているはずなのでフィードバックしておいた
* 8/28
  * https://salsa.debian.org/debian/libhinawa/-/merge_requests/6
    * libhinawa: revertする変更点のレビューを実施した
* 8/31
  * https://salsa.debian.org/debian/libhinawa/-/merge_requests/6
    * libhinawa: 変更点のレビュー実施
