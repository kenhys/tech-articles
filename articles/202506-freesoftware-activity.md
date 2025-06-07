---
title: "My Free Software Activities in June 2025"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

### 6月のハイライト


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
