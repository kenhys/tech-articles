---
title: "Debian: fabre.debian.netの開発の進め方と運用、得た学びの話"
emoji: "🪔"
type: "ideas"
topics: ["Debian"]
published: true
---

# fabre.debian.netの開発の進め方と運用、得た学びの話

これは[「個人アプリ/サービス開発の進め方と運用、得た学び - 02」の19日目の記事](https://qiita.com/advent-calendar/2020/lenovo_app_02/day/19)です。

## fabre.debian.netとは

Debianのバグトラッキングシステムは https://bugs.debian.org が使われています。
とても歴史のあるバグトラッキングシステムでシンプルなのですが、ちょっと使い勝手に難があります。
自分が欲しい機能をフィードバックするには時間がかかりそうなので、欲しいサービスを実験的に立ち上げてみました。

* https://fabre.debian.net

debian.netなのであくまで非公式なサービスに使われるドメインです。ある日突然畳むことがあるかもしれません。

fabre.debian.netで何を目指そうとしたのかについては、[An experiment about personalized front-end of bugs.debian.org](https://slide.rabbit-shocker.org/authors/kenhys/debconf2020-online/)としてDebConf20で発表をしました。ざっくりいうと、「(自分がメンテナンスしているわけではないけれども)まだ誰も直していない放置されているバグを簡単に探せるようにしたい」です。

https://udd.debian.org/dmd/ や https://qa.debian.org というのもありますが、自分がメンテナンスをしているパッケージに関して俯瞰できるようにするものです。
直接関わっているわけではない放置されているバグを探したりフィードバックしようとすると用途にはあまり向いていません。

## サービス開発の進め方と運用

自分のために開発したサービスなので、使っていて欲しくなった機能から順番に実装しています。思いつき駆動です。

* 欲しい機能やあったらいいかもな機能についてRedmineにチケットを立てておく
* 気が向いたらちまちま実装する
* 動作確認をしてfabre.debian.netにデプロイする

個人開発なので、ステージング環境には自宅に転がっていたシングルボードコンピューターを転用しています。

## サービスの運用で得た教訓

普段Webサービスの開発をまったくやっていないので、実際に手を動かしてみると、多くの教訓を得ました。
とはいっても、よくある基本的な事柄ばかりです。

* どんなにマイナーだろうがアタックはされる

インスタンスを立ち上げたときから、sshでログインしようと試みてきます。
きっちり公開鍵のみにアクセスをしぼりましょう。

* しつこい輩はbanする

何度もアタックをしかけてくるパターンについてはfail2banとかでガードしましょう。

* アクセス可能なポートを制限する

F/Wとかデフォルトでついているサービスもありますが、ufwとかでアクセス可能なポートはしめておきましょう。

* 定期的にリソースの使用状況を確認する

一番大事なのは、この点でした。というのも1vCPU 1GBメモリのインスタンスを使っているからです。
別に落ちたらそれまでのサービスですが、定期的にリソースは確認しましょう。
リソース監視系のサービスとか世の中にいっぱいありますが、collectdについてくるcollection3とかでもシンプルでよいです。

使っているのが自分一人とはいえ、メモリがやっぱり厳しいこととかわかります。
バッチを一緒にぶんまわしたら、インスタンスごと死ぬとかいうポンコツっぷりなんかも客観的にわかります。

* 使っていないサービスは無効化する

インスタンスの初期イメージがUbuntuだったのでそれを更新して使っているのですが、使っていないサービスはsystemctl disableできっちり止めておきましょう。
貧弱なサーバーリソースだと無駄なサービスは大敵です。

* フロントエンドのキャッシュを効かせる

一定のパターンのアクセスが多い場合には、nginxのキャッシュを設定しておくとよいです。貧弱なインスタンスなので、接続数なんかもある程度絞っていくほうがおすすめです。

* なんでもかんでもAWSにのっければよいわけではない

ふと思い立って t2.micro のインスタンスに乗っけてみたことがありますが、CPUクレジットの制限が厳しくて断念しました。
試行錯誤しつつCPUをぶんまわしている段階では、まだ早かったです。そういうことは別のタイプのインスタンスでやるべきですね。

## 今後の課題について

最近更新されたバグとか、RCなやつとかなんかはいい感じにリストアップできるようになってきたので、次はいい感じの全文検索を実装しようとしています。
1vCPUのインスタンスなので、負荷を抑えつつどこまでできるかがへの挑戦ですね。

## まとめ

https://fabre.debian.net の開発の進め方と運用、得た学びの話について書きました。
20日目は「skillfuls.devについてなにか書きます！」だそうです。
