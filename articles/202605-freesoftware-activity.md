---
title: "My Free Software Activities in May 2026"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 5月のハイライト

### 5月の活動記録

* 5/1
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1134707
    * aklomp-base64: new queueのbase64をrejectしてもらってaklomp-base64をアップロードした
* 5/2
  * https://github.com/groonga/groonga/pull/2798
    * groonga: GRN_WITH_TOOLS=ONでツールをインストールしたときのパスがおかしいのをフィードバックした
* 5/3
  * groonga: cmakeに移行するべく作業中。いろいろ面倒くさい。
* 5/4
  * fabre.d.nのbookwormからtrixieへのアップグレード実施
* 5/5
  * groonga: CMake対応したgroonga 16.0.1+dfsg-1をアップロードした。パッケージ追加しているので、new queueの審査を待つ必要がある
* 5/6
  * groonga: riscv64とs390xでのFTBFSに対応した
* 5/7
  * https://github.com/aklomp/base64/issues/103
    * aklomp/base64: base64を専有している件についてフィードバックした
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1135897
    * libh3: hppaでだけパッケージがない状態になっているのをバグ報告した
* 5/8
  * https://github.com/fluent/fluent-package-builder/pull/1045
    * groonga: ビルドシステムをAutotoolsからCMakeに変更したので閉じた
* 5/9
  * aklomp/base64: hurdを除外したり、使用方法等のREADME.Debianを更新してaklomp-base64 0.5.2-4をアップロードした
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1136009
    * deskflow: CVE-2026-41476に対応したdeskflow 1.26.0+dfsg-2をアップロードした
