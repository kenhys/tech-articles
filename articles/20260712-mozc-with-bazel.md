# Try to build Mozc with Bazel 7.7.1

## Introduction

Recently, I've got a chance to try building Mozc (Most famous Japanese input method editor) with Bazel.

As you know, recently newer Bazel related packages were landed into
debian/unstable.
Then now I'm planning to update Mozc from 2.29.5160.102
to 3.33.6133.

## Background story about Mozc and Debian

The upstream of Mozc had released 3.34.6239, but on Debian,
we stick to Mozc 2.29.5160.102.

Mozc requires newer Bazel but we only had Bazel 4.2.3 at that time on Debian, so even though the upstream of Mozc switched from GYP to Bazel,
we had patched Mozc with GYP based package.

We even did make an effort to restore build options that had been already removed. :-(
And needed to migrate from GTK2 renderer to GTK3 renderer.

That is why the version of Mozc is diverged from upstream on Debian.

* 2.29.5160.102 (Now on Debian)
* 2.29.5268.102
* 2.29.5374.102
* 2.29.5544.102
* 2.30.5544.102
* 2.31.5712.102
* 2.31.5851.102
* 2.32.5994.102
* 3.33.6089
* 3.33.6133 (Target to upgrade for)
* 3.34.6239

## How to switch from GYP to Bazel?

At first, we needed to decide what Mozc version to work with it.

Now latest version of Mozc is 3.34.x, but it requires Bazel 9.x.
Please recall that Bazel 7.7.1 was introduced Debian/unstable.
And more, newer dependency libraries are required.

You might feel that target version (3.33.6133) is too high from 2.29.5160.102,
but if we upgrade to more older Mozc, it means that it
requires to backport Mozc to older libabsl compatible codes and so on.

That is why Mozc 3.33.6133 was chosen.

Even once the target version has been decided, you can't let your guard down.

There are many technical tasks to solve.

* Revisit patch sets to apply
* Porting uim mozc patch and fix FTBFS
* Porting fcitx5 mozc patch and fix FTBFS
* Fix src/third_party vendoring
* Switch from GYP to Bazel build systems
* ...

At least, it will likely require several rounds of testing in the
Debian experimental.

## Conclusion

Currently, `gbp buildpackge` has succeeded finally on local machine, 
but need to tidy and cleanup stuffs.

I didn't know packaging with Bazel best practice yet, to remove many third party vendor/ bundles, I've found that it requires pile of patch to eliminate them.

In the current version of Debian, as a one of build system, further work — such as support from debhelper -
will be needed.

I'll file working progress on [#1085173](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1085173)
