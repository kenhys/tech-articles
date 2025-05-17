# 2025年のDebian sidで印象に残った不具合 n選

去年の記事は[2024年にDebian sidで踏んだ不具合8選](https://kenhys.hatenablog.jp/entry/2024/12/04/130508)です。

個人的に印象に残ったDebian sidで踏んだ不具合をピックアップしてみました。

(Debian sidそのものの不具合というよりかはupstreamの問題がパッケージ化されて広く使われるようになったことで踏みぬいたというケースも含んでいます。)

* 1月頃: [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1089513:title]
* 1月頃: [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1092081:title]
* 2月頃: [https://kenhys.hatenablog.jp/entry/2025/02/11/191558:title]
* 3月頃: [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1100078:title]
* 3月頃: [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1099191:title]
* 3月頃: [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1100486:title]
* 5月頃: [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1105784:title]

## [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1089513:title]

正確には2024年から継続していた不具合です。
DebianのリポジトリからインストールできるNvidiaのドライバー (535.216.03-1)がkernel 6.12に対応していない不具合でした。
Nvidiaのパッケージを更新しない場合、解像度が適切に設定できなかったりとはまるので、6.12にあげられない状態が続いていました。

linux-image-amd64をインストールしていると、既定で6.12で起動してしまうので、GRUBの設定で
回避する[https://kenhys.hatenablog.jp/entry/2025/01/13/172405:title]という記事を書きました。

nvidia-driver 535.216.03-2が2月にリリースされて問題は解消しました。

## [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1092081:title]

VirtualBoxがconfigureでpython 3.12までしかサポートしないようになっていたため、
Debian sidがpython3.13にあがったのに、VirtualBoxがPython 3.12に依存し続けて追従できないという不具合でした。

これによりPython 3.13をサポートした他のパッケージの更新がブロックされてしまうということが続いていました。
(ちょうどtrixie向けにせっせと皆がパッケージを更新しはじめていたので、手元で更新できないパッケージがたまっていった。)

VirtualBox 7.0.20-dfsg-1.2が2月にリリースされて不具合が解消しました。

## Breaking compatibility, upgrade from createrepo-c 0.17.3 to 1.2.0

これは不具合というか、パッケージの更新にともなう非互換を踏んでしまった例でした。

createrepo-cが 0.17.3から1.2.0にDebian unstableで更新されたのだけれども、
生成されるリポジトリのメタデータのフォーマットが変わってしまったことによる影響を受けた事例です。

従来は生成されるメタ情報はgz圧縮されていたのが、zstで圧縮されるのがデフォルトに変わったというものでした。

これにより、何も考えずに新しいバージョンのcreaterepo-cでリポジトリのメタデータを更新してしまうと、
リポジトリを参照している環境でyum経由で更新が一切できなくなります。

例えば、Amazon Linux 2なんかが新しいメタデータのフォーマットを扱えないので詰みます。
とはいえ、AlmaLinux 8,9とかAmazon Linux 2023なんかは問題ないので、影響は限定的です。

ソフトウェアの配布のためにリポジトリをメンテナンスしている人じゃないと気づかないし、
`--compatibility`オプションを指定して旧フォーマットのメタデータを生成しなおせばよいのでひとまずはそれで回避できます。

Amazon Linux 2は2026年6月までサポートが延長されたので、`--compatibility`オプションがcreaterepo-cから削除されたら
どうしようかなという気持ちはあります。

## [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1099191:title]

Debian installerでVMにDebianをインストールしようとするとミラーの選択が異様に遅い問題を踏みました。

よくよく調べてみると、VirtualBoxでブリッジネットワークを有効にしてインストールしようとすると、
IPv6で疎通できないため、タイムアウトしまくるという状況になっていました。

インストーラー内部で実行しているwgetはなんもオプションを指定しないとひたすら待つので
時間かかり過ぎてなんも処理がすすんでないように見えるというものでした。

どうやらVirtualBoxでWiFiのアダプタをブリッジ接続にしてゲストにDebianをインストールするような場合にはまる問題だとか。
ブリッジ接続ではなくNATだと問題を踏みません。
あるいは、グローバルアドレスにpingを打つと疎通できるようになるというハックが知られています。

この問題については、3月のDebian勉強会でも知見を共有しました。

* [Debian Installerがミラー選択で刺さる問題をどうにかする](https://slide.rabbit-shocker.org/authors/kenhys/tokyodebian-d-i-netcfg-202503/)

## [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1100078:title]

Budgie Desktop環境を利用しているのですが、gnome-shellなどの大量更新があった3/7あたりからデスクトップ環境に
ログインするとウィンドウマネージャがクラッシュするようになりました。

ディスプレイマネージャがgdm3とlightdmのどちらでも発生し、GNOME (クラシック)では問題が発生しないことから
Waylandがらみなんじゃないかなーと疑っていた事例でした。

もしかしたら、Debianでのパッケージング特有の問題かと思っていたのですが、そうではなくupstream自体の問題だったようです。

* [budgie-wm crashes on launch](https://bugs.launchpad.net/ubuntu/+source/budgie-desktop/+bug/2102655)

budgie-desktop 10.9.2-8でログイン時にクラッシュする問題は修正されました。

## [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1100486:title]

これは、grub2を不用意に更新すると起動しなくなって困るという不具合でした。
2.12-6に更新したか定かでない状態でバグ報告を目にして、ドキドキしながら翌日起動した記憶があります。

幸い、該当バージョンではあるものの特に支障なく起動できたので、問答無用で誰でも
起動しなくなるのではなく、特定条件を満たすと起動できなくなるパターンの不具合のようでした。

2.12-7の変更点をみるにNTFSがらみのリグレッションだったから踏まなかっただけのようです。

## [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1105784:title]

kvmモジュールが先に読み込まれていると、VirtualBoxが起動できなくなるという問題が以前ありました。

対策として設定ファイルを/etc/modprobe.d配下にインストールするはずが意図しない挙動により
反映されておらず、最近のlibkmodの更新でエラーとして検出されるようになったというもの。

手元の環境では/etc/modprobe.d/virtualbox.confとして対策していたので、問題に気づけていなかった。
