## Introduction

This is just a note-taking about how to upgrading Mozc package for up-coming trixie ready last year.

Maybe Mozc 2.29.5160.102+dfsg-1.3 will be shipped for Debian 13 (trixie).

# FTBFS with Mozc 2.28.4715.102+dfsg-2.2

In May 2024, I've found that Mozc was removed from testing, and still in FTBFS.

[https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1068186:title]

That FTBFS was fixed in the Mozc upstream, but not applied for a while.
Not only upstream patch, but also additional linkage patch was required to fix it.

Mozc is the de-fact standard input method editor for Japanese.
Most of Japanese uses it by default on linux desktop.

(Even though frontend input method framework is different, the background engine is Mozc in most cases - 
uim-mozc for task-japanese-desktop, ibus-mozc for task-japanese-gnome-desktop in Debian)

There is a case that Mozc was re-built locally with integrated external dictionary
to improve quantity of vocabulary. If FTBFS keep ongoing, it means that it blocks such a usage.
So I've sent patches to fix it and they were merged.

## Motivation to update Mozc

With fixing #1068186, I've also found Mozc version is not synced to upstream for a long time.

At that time, Mozc in unstable was version 2.28.4715.102+dfsg, but upstream already released 2.30.5544.102.
It seems that Mozc's maintainer was too busy and can't afford to update it, so I've tried to do it.

## The blockers for updating Mozc

But, it was not so easy task to do so.
If you want to package latest Mozc, there were many blockers.

* Newer Mozc requires Bazel to build, but there is no Bazel package to fit it (There is bazel-bootstrap 4.x, but it's old. v6.x or newer one is required.)
* Newer abseil and protobuf were required
* Renderer was changed to Qt. GTK renderer was removed
* Revise existing patchsets (e.g. for UIM, for Fcitx)

It was not all.

## Road to latest Mozc

First, I knew the existence of debian-bazel, so I've posted about bazel-packaging progress.

[https://lists.debian.org/debian-bazel/2024/07/msg00000.html:title]

Sadly there was no response from it.
Thus, it was not realistic to adopt Bazel as build tool chain.
In other words, we need to keep GYP patch and maintain it.

And as another topic, upstream changed renderer from GTK+ to Qt.

Here are the major topics about each release of Mozc.

* 2.30.5544.102 Require abseil 20240116.1 or later
* 2.29.5544.102 GYP was deprecated
* 2.29.5374.102
* 2.29.5268.102 No gtk renderer anymore, need Qt.
* 2.29.5160.102 
  * The last version that gtk renderer is available.
  * --use_gyp_for_ibus_build option was removed.
* 2.28.5029.102
* 2.28.4880.102
* 2.28.4715.102+dfsg Debian sid

The internal renderer change are too big, and before GYP deprecation
in 2.29.5544.102, GYP support was already removed gradually.

As a result, target to 2.29.5160.102 was the practical approach to make it forward.

## Revisit existing patchsets for 2.28.4715.102+dfsg

Second, need to revisit existing patchset to triage them.

* 0001-Update-uim-mozc-to-c979f127acaeb7b35d3344e8b1e40848e.patch 
  * Required
* 0002-Support-fcitx.patch 
  * Required
* 0003-Change-compiler-from-clang-to-gcc.patch
  * (maybe) Not needed anymore
  * Related commits:
    https://github.com/google/mozc/commit/ae169acdcc9f7c205a30d432486dcbf13dc3e316
    https://github.com/google/mozc/commit/aba090da42a8366e72bc320dfafc3f9f93755edf
* 0004-Add-usage_dict.txt.patch
  * Required. (maybe)
* 0005-Enable-verbose-build.patch
  * Required.
* 0006-Update-gyp-using-absl.patch
  * Required and need **massive** refactoring.
* 0007-common.gypi-Use-command-v-instead-of-which.patch
  * (maybe) Not needed anymore
* 0009-protobuf.gyp-Add-latomic-to-link_settings.patch
  * Required. 
* 0010-Fix-the-compile-error-of-ParseCommandLineFlags-with.patch
  * Required. Should be merged into 0006 patch.
* 0011-Fix-missing-abseil-gyp-link-settings.patch
  * Required. Should be merged into 0006 patch.

UIM patch was maintained in [third-party repository](https://github.com/e-kato/macuim),
and directory structure was quite different from Mozc.
It seems that maintenance activity was too low, so it was not enough that picking changes
from macuim. It was required to fix FTBFS additionally.

Fcitx patch was also maintained in [fcitx/mozc](https://github.com/fcitx/mozc).
But it tracks only master branch, so it was hard to pick patchset for specific version of Mozc.

Finally, I could manage to refresh patchset for 2.29.5160.102.

* support-uim.patch
* support-fcitx.patch
* change-compiler-from-clang-to-gcc.patch
* add-japanese-usage-dictionary.patch
* enable-verbose-build.patch
* update-gyp-using-system-abseil.patch
* gyp-using-command-instead-of-which.patch
* gyp-protobuf-link-with-atomic.patch
* enable-deprecated-gtk-renderer.patch
* fix-compile-error-of-ParseCommandLineFlags.patch
* enable-use_gyp_for_ibus_build-again.patch
* ibus-drop-needless-client_mock.patch
* protobuf-revert-internal-cleanup.patch
* uim-mozc-fix-ftbfs.patch

## Improve packaging task

Mozc need to be repacked, but it didn't use Files-Excluded yet.
So I've introduced d/watch to repack upstream source.

* [https://salsa.debian.org/debian/mozc/-/merge_requests/14:title]

It makes source package more reproducible.

## OT: Hardware breakage

There was another blocker to do this task.
I've hit the situation that g++ cause SEGV during building Mozc randomly.
First, I wonder why it fails, but digging further more, finally I've found that
memory module was corrupted. Thus I've lost 32GB memory modules. :-<

## Unexpected behaviour in uim-mozc

When uploaded Mozc 2.29.5160.102+dfsg-1 to experimental, 
I've found that there is a case that uim-mozc behaves weird.
The candidate words were shown with flickering.

But it was not regression in this upload.

uim-mozc with Wayland cause that problem.

Thus GNOME and derivatives might not be affected because ibus-mozc will be used.

## Mozc 2.29.5160.102+dfsg-1

As the patchset was matured, then uploaded 2.29.5160.102+dfsg-1 with --delayed 15 option.

```
$ dput --delayed 15 mozc_2.29.5160.102+dfsg-1_source.changes
Uploading mozc using ftp to ftp-master (host: ftp.upload.debian.org; directory: /pub/UploadQueue/DELAYED/15-day)
running allowed-distribution: check whether a local profile permits uploads to the target distribution
running protected-distribution: warn before uploading to distributions where a special policy applies
running checksum: verify checksums before uploading
running suite-mismatch: check the target distribution for common errors
running gpg: check GnuPG signatures before the upload
 signfile dsc mozc_2.29.5160.102+dfsg-1.dsc 719EB2D93DBE9C4D21FBA064F7FB75C566ED20E3

 fixup_buildinfo mozc_2.29.5160.102+dfsg-1.dsc mozc_2.29.5160.102+dfsg-1_amd64.buildinfo
 signfile buildinfo mozc_2.29.5160.102+dfsg-1_amd64.buildinfo 719EB2D93DBE9C4D21FBA064F7FB75C566ED20E3

 fixup_changes dsc mozc_2.29.5160.102+dfsg-1.dsc mozc_2.29.5160.102+dfsg-1_source.changes
 fixup_changes buildinfo mozc_2.29.5160.102+dfsg-1_amd64.buildinfo mozc_2.29.5160.102+dfsg-1_source.changes
 signfile changes mozc_2.29.5160.102+dfsg-1_source.changes 719EB2D93DBE9C4D21FBA064F7FB75C566ED20E3

Successfully signed dsc, buildinfo, changes files
Uploading mozc_2.29.5160.102+dfsg-1.dsc
Uploading mozc_2.29.5160.102+dfsg-1.debian.tar.xz
Uploading mozc_2.29.5160.102+dfsg-1_amd64.buildinfo
Uploading mozc_2.29.5160.102+dfsg-1_source.changes
```

Mozc 2.29.5160.102+dfsg-1 was landed at 2024-12-20.

## Additional bug fixes

Additionally, the following bugs were also fixed.

* [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1045435:title]

* [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1049806:title]

These bugs were fixed in [2.29.5160.102+dfsg-1.1](https://tracker.debian.org/news/1599998/accepted-mozc-2295160102dfsg-11-source-into-unstable/)

And more, I've found that even though missing pristine-tar branch commit, salsa CI succeeds.
I've sent MR for this issue and already merged into.

* [https://salsa.debian.org/salsa-ci-team/pipeline/-/merge_requests/505:title]

## Mozc and future in Debian

In this short journey, I gave up to updating more newer Mozc
because the version of dependency libraries were not updated.

* [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1081553:title]
* [https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1034668:title]

Note that protobuf 3.25.4 on experimental depends on older absl
20230802, so it must be rebuilt against absl 20240722.0.

And more, we need to consider how to migrate from GTK renderer to
Qt renderer in the future.
