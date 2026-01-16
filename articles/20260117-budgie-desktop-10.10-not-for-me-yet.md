# Budgie Desktop 10.10 is out, but not for me yet :(

## Introduction

I'm one of a Budgie Desktop user since 2020. (Budgie Desktop 10.5 or so)

Recently Budgie Desktop 10.10 had been available from 
Debian experimental.

I've tried it and realized that not for me yet.

## What is the requirement for desktop environment

* Screen sharing with specifying the specific window/application for web meeting
* Sharing keyboard input smoothly with deskflow
* Switch focus with mouse movement
* and ...

## Does Budgie Desktop 10.10 suitable?

Short answer: No, not yet.

It seems that Budgie Desktop 10.10 (wayland) lost the functionality
 - screen sharing with specifying the specific window/application for web meeting.

Of course, you can share your screen itself.

It also can't sharing keyboard input smoothly with deskflow.

Both of them seems that they are supported in GNOME.

In contrast to Budgie Desktop 10.9 (X11), Budgie Desktop 10.10 seems missing 
effective wayland + xdg-desktop-portal support for them yet.

It might be supported in the future release, but it might be 11.x.

## Alternatives?

Budgie Desktop will come into maintenance mode, so they will not be fixed in
10.x releases (guess).

https://buddiesofbudgie.org/blog/budgie-10-10-released

Switching DE might be option - GNOME or KDE. but 
I don't have much the energy to make the transition for now.

I decided to take the conservative option and go back to 10.9.

Note that if you upgrade to Budgie Desktop 10.10, it is hard to downgrade
to Budgie Desktop 10.9 because python3-gi, python3-gi-cairo dependency
blocks budgie-desktop. 

See https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1120138 for details.

As a dirty hack, you can modify python3-gi dependency and install it as your own risk.

## Conclusion

It was still too early to adopt Budgie Desktop (wayland) for me.
I'll stay with Budgie Desktop 10.9 for a while.

That said, it's unclear how long Budgie Desktop 10.9 will remain unstable and usable.
There might be a case that sticking to Budgie Desktop 10.9 might be problematic when other packages are updated.

When that happens, I'd like to reconsider this issue again.
