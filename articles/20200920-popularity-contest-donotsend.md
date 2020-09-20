---
title: "popularity-contestで特定のパッケージを除外するには"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: true
---

@[tweet](https://twitter.com/kenhys/status/1307536635093897222)

[#632438 - popularity-contest: a way to exclude certain packages - Debian Bug report logs](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=632438)

このバグにあるように、Debianのパッケージ調査に参加した場合、特定のパッケージのみ除外するような設定はありません。
したがって、特定のパッケージを除外したい場合には参加自体をとりやめるしか選択肢がありません。

例えば、個人的なパッケージを作成している場合や、開発中のパッケージを公開したくないような状況では、それらが含まれてしまうとノイズにしかならないので、除外したいと思うことがあります。
参加するかしないかだけでなく、パッケージ調査に参加しつつも、一部だけは除くことができるような選択肢がユーザーにあったほうがよいと考えました。

そこで、popularity-contestコマンドで特定のパッケージを除外できるような仕組みをいれる簡単なパッチを書いてみました。
Perlちっともわからないので見様見真似で書いたのがこんな感じのパッチです。

```perl
% diff -u popularity-contest-1.70.orig/popularity-contest popularity-contest-1.70/popularity-contest
--- popularity-contest-1.70.orig/popularity-contest     2020-03-31 02:47:56.000000000 +0900
+++ popularity-contest-1.70/popularity-contest  2020-09-20 13:08:25.858919252 +0900
@@ -28,6 +28,7 @@
 my $dpkg_db="/var/lib/dpkg/info";
 my $dpkg_origin="/etc/dpkg/origins/default";
 my $popcon_conf="/etc/popularity-contest.conf";
+my $donotsend_conf="/etc/popularity-contest.donotsend.conf";
 
 # $popcon_conf is in shell-script format
 my $HOSTID = qx(unset MY_HOSTID; . $popcon_conf; echo \$MY_HOSTID );
@@ -204,6 +205,19 @@
 
 close PACKAGES;
 
+# We do not send package name which is listed on /etc/popularity-contest.donotsend.conf.
+if ( -r $donotsend_conf && -s $donotsend_conf ) {
+    open DONOTSEND, $donotsend_conf;
+    while (<DONOTSEND>) {
+       chomp $_;
+       my $name = $_;
+       if (exists $popcon{$name}) {
+           delete $popcon{$name};
+       }
+    }
+    close (DONOTSEND);
+}
+
 # We're not done yet.  Sort the output in reverse by atime, and
 # add a header/footer.
 
```

たんに、パッケージ名が一致したら削除するだけの簡単なお仕事です。

あとは/etc/popularity-contest.donotsend.confにパッケージ名をずらずらとリストアップしておけば、そのパッケージに関する利用状況は送信されることはなくなるはずですね。
なお、上記のパッチはpopularity-contest-1.70向けですのでご注意あれ。
