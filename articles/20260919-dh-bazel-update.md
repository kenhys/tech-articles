# Building with dh-bazel, buildsystem support for debhelper experiment updates

## Introduction

After bazel-bootstrap 7.7.1 was landed into Debian unstable, 
I'm working on packaging newer Mozc (Most famous Japanese input method editor) with Bazel.

Here is the blog entry initial efforts to build Mozc with Bazel at that time.

[https://kenhys.hatenablog.jp/entry/2026/07/12/231009:embed:cite]

Then, I've shared implementing PoC `dh-bazel` experiment.
See why dh-bazel is needed, and prototype about `dh-bazel`.

[https://kenhys.hatenablog.jp/entry/2026/09/17/215331:embed:cite]

As a Bazel beginner, want to know what should pass to Bazel, what should not pass to Bazel.

## What is improved in recent dh-bazel?

In the previous versions of `dh-bazel`, it supports only basic features
to build with Bazel as a thin wrapper.

```
%:
        dh $@ --buildsystem=bazel

override_dh_auto_build:
        dh_auto_build -- //:hello
```

Now, with recent changes, it supports the following environment variables to resolve required system libraries in dynamically.

* `DH_BAZEL_OVERRIDE_MODULE`

It search the specified modules from bundled dummy modules in `dh-bazel`.
It accept ',' separated paramesters. (e.g. DH_BAZEL_OVERRIDE_MODULE=zlib,zstd).

`dh-bazel` bundles abseil-cpp, apple_support, buildozer, lz4, openssl, protobuf, rules_android_ndk, rules_apple, rules_swift, zlib and zstd as
dummy modules for ignored unused module and linking system libraries.

Now you can use it in `debian/rules` like this:

```
#!/usr/bin/make -f
# -*- makefile -*-
#

export DH_BAZEL_OVERRIDE_MODULE=zlib
export DH_VERBOSE=1

%:
        dh $@ --buildsystem=bazel --without=single-binary

override_dh_auto_build:
        dh_auto_build -- //:hello
```

It is impossible to cover all of system libraries in Debian, so in that case, please consider to use the following `DH_BAZEL_PKGCONF_MODULE`.

* `DH_BAZEL_PKGCONF_MODULE`

It search the specified modules with pkgconf. It is useful when there is no bundled modules in dh-bazel if you want.
It accept ',' separated paramesters. (e.g. DH_BAZEL_PKGCONF_MODULE=gtk4-x11,gtk4-unix-print).

If DH_BAZEL_PKGCONF_MODULE could not match, then dh-bazel fallback to dig into Build-Depends: field
in debian/control. Note that if it is not deterministic (e.g. -dev package provides multiple .pc files)
dh-bazel gives up fallback with pkgconf.

Now you can use it in `debian/rules` like this:

```
#!/usr/bin/make -f
# -*- makefile -*-
#

export DH_BAZEL_PKGCONF_MODULE=gtk4-x11,gtk4-unix-print
export DH_VERBOSE=1

%:
        dh $@ --buildsystem=bazel --without=single-binary

override_dh_auto_build:
        dh_auto_build -- //:hello
```


## Conclusion

dh-bazel is still in very early stage prototype, but it resolves some sort of packaging glitches a bit by bit.

I hope that it will help package maintainer using Bazel.
(dh-bazel is not uploaded into debian/unstable yet, so stay tuned!) 
