---
title: "Debian: Say Good-Bye and Thanks hal-flash"
emoji: "🪔"
type: "tech"
topics: ["Debian"]
published: false
---

Today, hal-flash package was removed from Debian unstable.

hal-flash is wrapper library for HAL which is not used nowadays.
At that time, HAL was required because Adobe Primetime DRM uses libadobecp, but HAL was already replaced to udev or udisks.
So we need emulation layer for HAL. hal-flash was it for such a purpose.
(At least, hal-flash is required to play hulu.jp movies which uses Adobe DRM)

hal-flash package was already orphaned years ago, and removed from unstable now.

[O: hal-flash -- Compatibility library to allow playback of Flash DRM content](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=931898)

Thanks hal-flash package!
