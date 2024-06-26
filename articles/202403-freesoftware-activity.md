---
title: "My Free Software Activities in March 2024"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

* 3/3
  * groonga-normalizer-mysql 1.2.3-2をアップロードした。libgroonga0t64に対応するため。
* 3/8
  * https://bugs.debian.org/1065647
    * lists.debian.orgのカテゴリ分けがわかりにくい気がするのでフィードバックした。
* 3/11
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1066031
    * groongaが依存するzeromq3のせいでBD-Uninstallableなのでgiven-backしてもらうようにフィードバックした。
* 3/12
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1066031#10
    * given-backは対象となる依存先のパッケージがInstalledな状態では実行できないっぽい。その場合はnmuとしてリクエストすべきなようだ。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1066519
    * givebackアクションをInstalledなパッケージに対して実行できないのでフィードバックしておいた。
* 3/23
  * libhinawa 4.0.1-2.1のNMUをリポジトリに反映した
  * libhinawa 4.0.1-2.2のNMUをリポジトリに反映した
  * groonga-normalizer-mysql Depends: libgroonga0t64が不要なので削除して1.2.3-3としてアップロードした。
  * groonga 13.1.1+dfsg-1.1でpkg-configへのBuild-Depends:がE:扱いになるので、13.1.1+dfsg-2としてアップロードした。
  * groonga 13.1.1+dfsg-2でpkg-configへのDepends:の修正漏れがあったので、13.1.1+dfsg-3としてアップロードした。
  * https://salsa.debian.org/debian/grow-your-ideas/-/issues/44
    * armelやarmhfのbuilddリソースが足りてなさそうなので、既存のbuilddを一部共用できないか案をだしてみた。
  * https://kenhys.hatenablog.jp/entry/2024/03/23/211515
    * issues#44 をPlanetDebianに記事として投稿してみた。
* 3/24
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1067585
    * groonga-normalizer-mysql 1.2.3-3で修正済みなので、クローズした。
  * http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1067603
    * contextfreeがarmel,armhfでビルドできないのをフィードバックした。
* 3/27
  * http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1067837
    * tremotesf 2.6.0-1がarmelでftbfsなのをフィードバックした。
  * http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1067839
    * triton 2.0.0.post1-4がarmelでftbfsなのをフィードバックした。
* 3/28
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1067839
    * tritonのseverityをimportantからseriousに変更。ftbfsなので。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1067603#12
    * contextfreeで質問がきていたのでフィードバックした。
* 3/29
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1067952
    * mes 0.26-1のftbfsをフィードバックした。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1067954
    * openmesh 9.0-4のftbfsをフィードバックした。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1067956
    * roalution 5.7.1-2のftbfsをフィードバックした。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1067958
    * ruy 0.0.0~git20230215.21a85fe-1のftbfsをフィードバックした。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1067959
    * sambamba 1.0.1+dfsg-1のftbfsをフィードバックした。
* 3/30
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068051
    * tilix 1.9.6-2のftbfsをフィードバックした。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068052
    * openms 2.6.0+cleaned1-4のftbfsをフィードバックした。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068054
    * rauc 1.11.3-1 armel,armhfのftbfsをフィードバックした。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068055
    * ccls 0.20230717-1 armelのftbfsをフィードバックした。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068056
    * ccls 0.20230717-1 armhfのftbfsをフィードバックした。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1041803
    * hyperspy: ftbfsタグがなかったので付与した
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068057
    * libgtkada 24.0.0-2 armelのftbfsをフィードバックした。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068058
    * libgtkada 24.0.0-2 armhfのftbfsをフィードバックした。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068063
    * sssd 2.9.4-1.1 armel, armhfのftbfsをフィードバックした。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068065
    * quorum 1.1.2-2 armel, armhf, i386のftbfsをフィードバックした。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068066
    * docker-registry 2.8.2+ds1-1 armhfのftbfsをフィードバックした。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068067
    * fpzip 1.3.0-3 armel,armhf,i386のftbfsをフィードバックした。
  * https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1065647
    * debian-wwwにProposal:として提案してみた。
* 3/31
  * groonga-normalizer-mysql 1.2.3-4をアップロードした。
  * https://mentors.debian.net/package/libhitaki/
    * libhitaki 0.2.1-2をスポンサーアップロードした。
  * https://mentors.debian.net/package/libhinoko/#upload-1
    * libhinoko 1.0.1-4についてレビューした。
