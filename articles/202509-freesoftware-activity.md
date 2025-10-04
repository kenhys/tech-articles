---
title: "My Free Software Activities in Sep 2025"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 9月のハイライト

9月は従来だましだまし延命していたPCパーツをようやくえいやと交換して、作業環境を改善した。

Debian方面だとGCC 15が投入されたり、CMake 4投入など、FTBFS祭りが始まったのが印象深い。

他にも印象に残った不具合としては、VirtualBoxのVMを起動できなくなった #1114886 があった。
作業環境が変わったが、M.2はそのまま再利用したせいで、VirtualBoxのカーネルモジュールが
読み込まれなくてVMを起動できなかったというもの。
これは結局手元の環境の問題で、MOK Managerで鍵を登録しないといけないのを失念していたせいだった。

### 9月の活動記録

* 9/2
  * https://salsa.debian.org/rocm-team/pkg-rocm-tools/-/merge_requests/2
    * pkg-rocm-tools: フィードバックに対応。もっとシンプルにチェックできたので改善
* 9/4
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1112883
    * fasttext: CMake 4でFTBFSが発生する問題への対処 0.9.2+ds-9としてアップロード
* 9/5
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1097872
    * sentencepiece: GCC 15のftbfsの対応状況のフィードバック
    * 0.2.1で修正されていたので、sentencepiece 0.2.1-1 をアップロード Closes: 1097872, 1113496
* 9/7
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1096779
    * groonga: GCC 15のftbsを修正して15.1.5+dfsg-2としてアップロードした
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1096783
    * growl-for-linux: GCC 15のftbfsを修正した 0.8.5-10としてアップロードした
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1112233
    * growl-for-linux: 不必要なdbus-glibへのBuild-Dependsを削除した
* 9/10
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1114213
    * mozc: ftbfsに関するパッチをバックポートしておいた。RISC-V特有じゃないのでパッチ名は変えた。
* 9/12
  * https://github.com/paulproteus/public-udd-mirror/issues/25
    * udd-mirror: udd-mirrorが同期しなくなっていたのでフィードバックした
* 9/13
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1112890
    * fcitx-dbus-status: CMake 4のftbfsの問題を修正した
  * groonga-normalizer-mysql: 1.2.9-1をアップロードした
* 9/21
  * https://github.com/paulproteus/public-udd-mirror/issues/25
    * udd-mirror: 問題が解消しているようなので閉じた
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1114886
    * virtualbox: securebootがらみでvirtualboxのVMを起動できなかった件を閉じた
  * https://github.com/rvm/rvm/pull/5588
    * rvm: Ruby 3.4.6対応のフィードバック
* 9/24
  * https://github.com/paulproteus/public-udd-mirror/issues/24
    * udd-mirror: udd-mirrorがまだ不安定な結果を返すので再現条件をフィードバックした
* 9/28
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1112811
    * createrepo-c: CMake 4でFTBFSになる問題へとフィードバックした
  * https://salsa.debian.org/pkg-rpm-team/createrepo-c/-/merge_requests/2
    * createrepo-c: CMake 4対応のフィードバック
