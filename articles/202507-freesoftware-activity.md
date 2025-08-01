---
title: "My Free Software Activities in July 2025"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 7月のハイライト

trixieリリースが控えていたので、deskflowを更新して投入した。
主要なパッケージではないため、パッチリリースでなくても20日待てば投入可能であった。

Debian関連だと、d/watchのバージョン5というのが提案され、実際に投入されはじめたので
deeplearning-teamとかrocm-team配下のリポジトリへと実際にフィードバックした。
d/watch 5への移行はuscanで実行できるので機械的に適用するだけで楽である。

あとは、Fluentdプラグインの良くない書き方なんかを指摘するカスタムCopを開発したのが成果。
元々はプラグインのコードを対象にしていたが、Fluentd本体の修正にも寄与することができた。

### 7月の活動記録

* 7/1
  * deskflow: 1.22.0+dfsg-5をアップロードした。autopkgtestが壊れていたのを修正した。
* 7/2
  * deskflow: 1.22.0+dfsg-7をアップロードした。s390xのせいでマイグレーションが成功しない。
* 7/3
  * https://www.debian.org/devel/debian-installer/errata.ja.html
    * debian-installerのerrta情報を更新した
  * https://github.com/deskflow/deskflow/pull/8728
    * deskflow: manの生成に関してフィードバックを反映した
* 7/5
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1108813
    * deskflow: s390xのバイナリパッケージを削除するようにフィードバック
* 7/7
  * rubocop-fluentd 0.1.0をリリース。Fluentdプラグインのコードをチェックできるようになった。
* 7/9
  * rubocop-fluentd 0.1.1をリリース。config_paramのバグを検出できるようになった。
* 7/10
  * rubocop-fluentd 0.2.0をリリース。autocorrectionに対応した。このへんのノウハウを残しておきたい
* 7/14
  * fluent-plugin-fluent-package-update-notifier 0.2.0をリリース。将来の追加リリースにも追従できるようにした。
* 7/17
  * https://github.com/rvm/rvm/pull/5574
    * ruby 3.4.5がリリースされたので追従するためのフィードバック
* 7/19
  * https://github.com/fluent/fluentd/pull/5028
    * fluentd: globalなロガーをプラグインで使用しないようにするフィードバック
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1037256
    * debian installer: 日本語フォントの問題が修正されているので閉じておいた
  * https://salsa.debian.org/debian/devscripts/-/merge_requests/520
    * lintian: v5フォーマットに関してフィードバックをした
* 7/22
  * https://github.com/paulproteus/public-udd-mirror/issues/23
    * udd-mirror: ミラーの同期がPostgreSQLの行進のせいでとまっていたのでフィードバックした
* 7/28
  * https://salsa.debian.org/rocm-team/amdsmi/-/merge_requests/1
  * https://salsa.debian.org/deeplearning-team/cpuinfo/-/merge_requests/5
  * https://salsa.debian.org/deeplearning-team/fp16/-/merge_requests/3
  * https://salsa.debian.org/deeplearning-team/fxdiv/-/merge_requests/3
  * https://salsa.debian.org/deeplearning-team/ggml/-/merge_requests/2
  * https://salsa.debian.org/deeplearning-team/gloo/-/merge_requests/1
  * https://salsa.debian.org/rocm-team/half/-/merge_requests/2
  * https://salsa.debian.org/rocm-team/hipblas/-/merge_requests/1
  * https://salsa.debian.org/rocm-team/hipblas-common/-/merge_requests/1
  * https://salsa.debian.org/rocm-team/hipcub/-/merge_requests/1
  * https://salsa.debian.org/rocm-team/hipfft/-/merge_requests/1
  * https://salsa.debian.org/rocm-team/hipify/-/merge_requests/1
  * https://salsa.debian.org/rocm-team/hipsolver/-/merge_requests/1
  * https://salsa.debian.org/rocm-team/hipsparse/-/merge_requests/1
  * https://salsa.debian.org/deeplearning-team/huggingface_hub/-/merge_requests/1
  * https://salsa.debian.org/deeplearning-team/ideep/-/merge_requests/2
  * https://salsa.debian.org/deeplearning-team/kleidiai/-/merge_requests/1
  * https://salsa.debian.org/deeplearning-team/libnop/-/merge_requests/3
  * https://salsa.debian.org/deeplearning-team/llama.cpp/-/merge_requests/3
  * https://salsa.debian.org/deeplearning-team/lodepng/-/merge_requests/1
  * https://salsa.debian.org/rocm-team/miopen/-/merge_requests/11
  * https://salsa.debian.org/deeplearning-team/mujoco/-/merge_requests/1
  * https://salsa.debian.org/deeplearning-team/neon-2-sse/-/merge_requests/1
  * https://salsa.debian.org/deeplearning-team/onnx/-/merge_requests/3
  * https://salsa.debian.org/deeplearning-team/onnxruntime/-/merge_requests/5
  * https://salsa.debian.org/deeplearning-team/onnxscript/-/merge_requests/1
  * https://salsa.debian.org/deeplearning-team/python-openai/-/merge_requests/1
  * https://salsa.debian.org/deeplearning-team/pytorch/-/merge_requests/7
  * https://salsa.debian.org/deeplearning-team/pytorch-audio/-/merge_requests/1
  * https://salsa.debian.org/rocm-team/rccl/-/merge_requests/1
  * https://salsa.debian.org/rocm-team/rocalution/-/merge_requests/1
  * https://salsa.debian.org/rocm-team/rocblas/-/merge_requests/2
  * https://salsa.debian.org/rocm-team/rocdbgapi/-/merge_requests/2
  * https://salsa.debian.org/rocm-team/rocm-cmake/-/merge_requests/6
  * https://salsa.debian.org/rocm-team/rocm-hipamd/-/merge_requests/8
  * https://salsa.debian.org/rocm-team/rocm-llvm/-/merge_requests/1
  * https://salsa.debian.org/rocm-team/rocm-smi-lib/-/merge_requests/7
  * https://salsa.debian.org/rocm-team/rocminfo/-/merge_requests/6
  * https://salsa.debian.org/rocm-team/rocprim/-/merge_requests/2
  * https://salsa.debian.org/rocm-team/rocr-runtime/-/merge_requests/8
  * https://salsa.debian.org/rocm-team/rocsolver/-/merge_requests/1
  * https://salsa.debian.org/rocm-team/rocsparse/-/merge_requests/2
  * https://salsa.debian.org/rocm-team/roct-thunk-interface/-/merge_requests/6
  * https://salsa.debian.org/rocm-team/rocthrust/-/merge_requests/3
  * https://salsa.debian.org/rocm-team/roctracer/-/merge_requests/1
  * https://salsa.debian.org/deeplearning-team/ruy/-/merge_requests/2
  * https://salsa.debian.org/deeplearning-team/safeint/-/merge_requests/1
  * https://salsa.debian.org/deeplearning-team/safetensors/-/merge_requests/1
  * https://salsa.debian.org/deeplearning-team/xgboost/-/merge_requests/2
    * debian/watch 5に対応するフィードバック実施
