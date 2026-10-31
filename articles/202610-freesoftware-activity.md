---
title: "My Free Software Activities in October 2026"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 10月のハイライト

Mozcに関連して、uim関連の整備を手伝ったりしたのが10月の目立った成果。
また、Mozcの各環境での検証作業を楽にするために、[virt-japanese-desktop](https://salsa.debian.org/kenhys/virt-japanese-desktop)を開発した。
virt-japanese-desktopについては、小江戸らぐ10月のあつまりにオンラインで参加したときに紹介したりもした。

ここ数ヶ月地道に対応をすすめてきたMozcの3.33.6133+ds1-0.2をunstableに投入できたのも
よかった。事前にexperimentalで気になるところを潰しておいたので、いまのところ致命的な不具合報告とかはない。

### 10月の活動記録

* 10/1
  * https://salsa.debian.org/debian/uim/-/merge_requests/35
    * uim: uim-mozcのArchitecture:がanyになっているが、Mozc 2.29では提供している環境を制限しているので修正した。Mozc 3.33がacceptされるとまた状況は変わってくる。
* 10/3
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1149398
    * uim: MR!35に関してコメントしておいた
  * https://salsa.debian.org/debian/uim/-/merge_requests/36
    * uim: maintainer modeに関するレビュー実施
* 10/4
  * https://salsa.debian.org/kenhys/virt-japanese-desktop
    * virt-managerでイメージのスナップショットを最新に追従していくのが面倒臭すぎたので、都度環境をつくりなおせるスクリプトを開発した。debvmではなく、virt-customizeを活用したスクリプトから構成されている。
* 10/5
  * https://salsa.debian.org/debian/uim/-/merge_requests/37
    * uim: 1:1.9.8-2の変更点のレビューをした
  * https://salsa.debian.org/kenhys/virt-japanese-desktop
    * virt-japanese-desktopでKDEにも対応した。
* 10/6
  * https://salsa.debian.org/kenhys/virt-japanese-desktop
    * virt-japanese-desktop: 確認ダイアログを実装して0.9.5とした
* 10/7
  * https://salsa.debian.org/kenhys/virt-japanese-desktop
    * virt-japanese-desktop: budgieに対応した
  * https://salsa.debian.org/debian/uim/-/merge_requests/39
    * uim: wb86とzm削除にかんするレビュー実施
* 10/9
  * groonga: 16.1.3+dfsg-1をアップロードした。32bitはMRB_INT32を適用するようにした。
  * virt-japanese-desktop: 0.9.7をリリース。
* 10/10
  * https://github.com/VOICEVOX/voicevox_core/pull/1459
    * voicevox_core: MIGraphXをサポートするフィードバック
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1150463
    * debusine: work-request signに影響する旨をフィードバック
  * https://koedolug.connpass.com/event/407537/
    * 小江戸らぐ10月のオフな集まりにオンラインに参加した
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1150493
    * groonga: 16.1.3+dfsg-2としてアップロードした
  * deskflow: 1.27.0+dfsg-1をアップロードした
  * https://salsa.debian.org/deeplearning-team/onnxruntime/-/merge_requests/11
    * onnxruntime: MIGraphXが有効になっていないのでフィードバックした
* 10/11
  * debianのonnxruntimeとmigraphxでvoicevox_coreを使えるか調査
* 10/12
  * https://github.com/hiroyuki-komatsu/japanpost_zipcode/pull/3
    * japanpost_zipcode: 定期的に更新してくれるやつを用意した
* 10/13
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1130733
    * mozc: 3.33.6133+ds1-0.1でppc64elサポートしたのでクローズした
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=981269
    * mozc: abseil bundle化に関してwontfixにしておいた
  * https://salsa.debian.org/debian/uim/-/merge_requests/40
    * uim: multi-arch等のレビュー実施
  * https://salsa.debian.org/debian/uim/-/merge_requests/41
    * uim: wrap-and-sort -a結果のレビュー実施
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=985709
    * mozc: mozc-toolがKDE Qt theme無視する問題について最新版で試して再現してないし、元の報告はbullseye時代のやつなので閉じた
* 10/15
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1150949
    * zstd-jni-java: mozcが間接的に依存しているが、JNIがまともにビルドできていないのでフィードバックした
  * dfsg-reviewのフィードバックを反映してmozc: mozc 3.33.6133+ds1-0.2をアップロードした
* 10/18
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1150975
    * mozc: 3.34.6239+ds1-0.1~exp1をexperimentalにアップロードした
* 10/20
  * https://lists.debian.or.jp/mailman3/hyperkitty/list/debian-devel@debian.or.jp/thread/VEKKWLACJ27PPTC2E6SUBR6XGMCNXNJB/
    * mozc: debian-develとdebian-usersにMozc 3.34.6239+ds1-0.1~exp1の動作確認依頼のメールを投げた
* 10/22
  * https://salsa.debian.org/debian/uim/-/merge_requests/43
    * uim: mozcのサポート対象が変わっているのでそれに追従するためのフィードバックをした
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1149540
    * hipblaslt: experimentalのバージョンがあればFTBFSの問題は解消しそうに思えるのでフィードバックした
* 10/24
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1151519
    * bazel-buildtools: リポジトリの移転をフィードバックしている点をコメント
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1150813
    * mozc: uim側にサポートされているアーキテクチャに関してフィードバックしてマージしてもらっていることをコメント
* 10/26
  * bazel-buildtools: dfsg-teamフィードバック修正
  * https://salsa.debian.org/debian/uim/-/merge_requests/44
    * uim: 1:1.9.9-2のreview実施
* 10/27
  * https://salsa.debian.org/debian/uim/-/merge_requests/45
    * uim: IBusインテグレーションのパッケージを追加するフィードバック
* 10/30
  * https://salsa.debian.org/debian/uim/-/merge_requests/46
    * uim: サポートされているアーキテクチャの更新漏れを修正
