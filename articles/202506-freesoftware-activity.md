---
title: "My Free Software Activities in June 2025"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 6月のハイライト

今月は、Debian Installerを使ってグラフィカルインストールを日本語で行おうとすると
一部のグリフが期待通りに表示されない、いわゆる中華フォントの問題が修正されたことが大きなトピックであった。
インストーラーへと組み込む修正自体はDebian Installerに関するキーパーソンであるCyrilさんが実施したのだけれど、
事前の検証とかフォントパッケージに関する修正あたりなんかは協力して行えたのは成果である。

Debian 13のhard freezeなのでやや無理やりねじ込んだ感じはあるものの、Debian 13 (trixie)に間に合ったのは喜ばしい。
Debian 9から発生していた地味な問題をようやく解決にもっていけた。

この件については、Debian勉強会でも発表したし、記事にもしておいた。

* [Fixing long standing font issue about Debian Graphical Installer](https://kenhys.hatenablog.jp/entry/2025/06/16/203655)

あとは、毎回ぎりぎりになっていた、Debian勉強会の発表内容を原稿化する作業も終わった。
「あんどきゅめんてっどでびあん」の夏号として収録されるはずである。

また、普段利用しているキーボードのUHK 60 v2向けに、専用のRiser 60を購入した。
標準のチルトだと、たまにぐらついて使い勝手が悪かったのだが、Riser 60を導入することで
ぐらつきが一切なくなったのでかなり改善した。ハンガリーからの個人輸入になるのでちょっとお財布には優しくなかった。
(10度の傾きを安定的に確保するための出費と考えるとたぶんコスパはものすごく悪いんだろうが、時間を買ったのだ。。。)

### 6月の活動記録

* 6/1
  * deskflow: 1.22.0+dfsg-1をアップロードしたら、big endianでテストが失敗する問題に対処した。experimentalに1.22.0+dfsg-1はアップロードしたほうがよかったかもしれない。autopkgtestがないので、unblockリクエストしないとtestingには投入されないし、仮に1.21.2にバグがあったら対処しないといけないからである。
  * https://github.com/deskflow/deskflow/discussions/8642
    * deskflow: big endianのテストで失敗しているのでサポートの有無についてフィードバック
* 6/2
  * deskflow: big endianで失敗するテストをスキップするのはやはり筋が悪いので1.22.0+dfsg-3をアップロード
* 6/4
  * https://salsa.debian.org/fonts-team/fonts-motoya-l-cedar/-/merge_requests/1
    * fonts-motoya-l-cedar: MRへの協力を依頼している
* 6/7
  * Debian勉強会の資料を作成
* 6/13
  * Debian勉強会の資料更新
* 6/14
  * https://debianjp.connpass.com/event/357138/
    * Debian勉強会でDebian Installerにおける日本語フォントの問題について発表した
* 6/16
  * https://kenhys.hatenablog.jp/entry/2025/06/16/203655
    * Debian Installerの日本語の問題が修正されたことを記事にした
* 6/17
  * https://salsa.debian.org/tokyodebian-team/minidebconf-japan-2025/-/merge_requests/1
    * MiniDebConf 2025 JapanのサイトでCoCのリンクに関してフィードバック
* 6/21
  * https://github.com/deskflow/deskflow/issues/8711
    * deskflow: Waylandのみの環境向けのビルドサポートに関してフィードバック
* 6/24
  * あんどきゅめんてっどでびあん2025年夏号 2025年3月のインストーラーが刺さる件の原稿まとめ
* 6/27
  * あんどきゅめんてっどでびあん2025年夏号 2025年6月のインストーラーのフォントの原稿まとめ
* 6/28
  * https://www.debian.org/releases/trixie/release-notes/issues.ja.html#reduced-support-for-i386
    * リリースノートの一部翻訳のフィードバック
* 6/30
  * https://salsa.debian.org/mirror-team/masterlist/-/merge_requests/14
    * ftp.kddilabs.jpが停止するということなのでフィードバックを送っておいた
  * https://github.com/deskflow/deskflow/pull/8728
    * deskflowがhelp2manを利用して生成するmanに関してフィードバック
  * deskflow: autopkgtest対応を追加したdeskflow+dfsg-4 をアップロードした

