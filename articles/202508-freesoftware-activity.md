---
title: "My Free Software Activities in Aug 2025"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 8月のハイライト

8月は、AMDGPUに変更してからおよそ一ヶ月経過した。
ROCmまわりを触ってみたいと思っているが、まだそれほど遊べていない。

先月実施したdebian/watch version 5への移行フィードバックも、devsciptsがリリースされたことで
マージされていっている。自分がメンテナンスしているやつもd/watch 5にしている。

Fluent Packageのv6をなんとかリリースできたことは喜ばしい。

### 8月の活動記録

* 8/1
  * https://github.com/fabric8io/fluent-plugin-kubernetes_metadata_filter/pull/404
    * Fluentd v1.19.0がリリースされたのでフィードバック
  * https://github.com/rvm/rvm/pull/5578
    * rvm: Ruby 3.3.9がリリースされていたのでフィードバック
* 8/2
  * https://salsa.debian.org/rocm-team/rocm-llvm/-/merge_requests/1
    * rocm-llvm: masterで対処されたのでクローズ
  * https://salsa.debian.org/rocm-team/miopen/-/merge_requests/11
    * miopen: masterにMRを追従した
* 8/9
  * deskflow: 1.23.0+dfsg-1をアップロードした
* 8/10
  * groonga: 15.1.4+dfsg-1をアップロードした
  * groonga-normalizer-mysql: 1.2.8-1をアップロードした
  * migraphx: debian-ai ML 2025-08-07 Meeting Logsのmigraphxの問題についてフィードバックした
* 8/15
  * https://github.com/deskflow/deskflow/issues/8859
    * deskflow: フィードバックしたコードのLGPL3-or-laterに同意
* 8/19
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1111451
    * deskflow: autopkgtestでsbuildが失敗するという報告があったのでコメント
  * deskflow: 1.23.0+dfsg-2をdebusineを使ってアップロードしてみた
* 8/20
  * https://github.com/DIGImend/digimend-kernel-drivers/pull/714
    * digimend-dkms: 6.xならtimer_delete_syncに置き換えてしまっていいだろうというというPRに対してフィードバック
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1106548
    * digimend-dkms: 6.15対応して13-5をアップロードした。すでにexperimentalは6.16が開発中だったので6.16で確認済み
  * https://github.com/fluent-plugins-nursery/fluent-plugin-kubernetes_metadata_filter/pull/405
* 8/26
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1111451
    * deskflow: autopkgtestの設定の問題のためクローズした。
* 8/30
  * groonga: 15.1.5+dfsgをアップロードした
* 8/31
  * https://salsa.debian.org/rocm-team/pkg-rocm-tools/-/merge_requests/2
    * pkg-rocm-tools: IOMMUを無効にしているとスクリプトエラーとなって途中で終了してしまうのでフィードバック
