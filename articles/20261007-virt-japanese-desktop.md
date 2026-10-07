# Testing Japanese IMEs on virtual desktops with virt-japanese-desktop

Japanese input method editors (IMEs) such as **Mozc** are essential for typing
Japanese. Testing them is a surprisingly fiddly job: an IME behaves differently
depending on the desktop environment (GNOME, KDE, Xfce, Budgie), the input
framework (ibus, fcitx5, uim), and the Wayland or X11 session. Setting up a
fresh VM for every combination from scratch is slow and repetitive, and
breaking your host's environment while experimenting is no fun.

`virt-japanese-desktop` is a small set of scripts that solves exactly this
problem. It builds ready-to-use virtual machines - each with a desktop
environment and a Japanese IME already installed and configured - so you can
start typing Japanese within a minute of booting, and throw the whole thing
away without any impact on your host.

## What it gives you

A single `make` command produces a qcow2 image that combines one of four
desktops with one of three IMEs:

|  | ibus-mozc | fcitx5-mozc | uim-mozc |
| --- | --- | --- | --- |
| **GNOME** | ✓ | ✓ | ✓ |
| **KDE** | ✓ | ✓ | ✓ |
| **Xfce** | ✓ | ✓ | ✓ |
| **Budgie** | ✓ | ✓ | ✗ |

The one gap — **uim on Budgie** — is a real technical limitation, not an
oversight: Budgie runs the labwc compositor, which implements
`zwp_input_method_v2`, while `uim-wayland` only speaks the older
`zwp_input_method_v1` (KWin/Weston). On Budgie you use ibus-mozc or fcitx5-mozc
instead.

All images come with the Japanese locale, fonts, and the `Asia/Tokyo` time
zone pre-configured, plus the SSH key of your choice. Input switching is wired
up out of the box: **Ctrl + Space** or **Shift + Space** for your IMEs to enable it.

## The layered-image trick

The core idea is that the images are **stacked qcow2 overlay layers**, one on
top of another:

```
debian-sid-nocloud-amd64-daily.qcow2     ... base image you download
└─ unstable-japanese-template.qcow2      ... locale, fonts, user, SSH
   └─ unstable-<DE>-template.qcow2       ... a desktop environment
      └─ unstable-<DE>-<IME>.qcow2       ... desktop + IME, configured
         └─ unstable-<DE>-<IME>.workspace.qcow2 ... the image you test in
```

This makes both **building and resetting fast**. The first build downloads and
customizes the base image and takes a while, but every later step only adds a
thin overlay. When a test breaks the VM, you do not rebuild anything - you
simply delete the top *workspace* layer and recreate it. That is all it takes
to return to a pristine state:

```sh
rm /tmp/unstable-gnome-ibus-mozc.workspace.qcow2
make gnome-ibus-mozc
```

The images reference their backing files by **relative path**, so you can move
an entire stack anywhere you like as long as the images stay together.

## A platform for experimenting with bleeding-edge IMEs

The base system is Debian **unstable (sid)**, and the `experimental`
repository is already added. That makes the project a convenient platform for
testing not just the IME packages in sid but also the ones still being
developed in `experimental` - exactly what the project was built for.

The keyboard layout of the VM follows the layout of your host (read from
`/etc/default/keyboard`, with a fallback chain to `localectl` and finally
`us`).

## Quick start

```sh
# 1. Install the tools (Debian/Ubuntu example)
sudo apt install qemu-utils libguestfs-tools virt-install curl

# 2. Save your SSH public key
curl --location https://github.com/USERNAME.keys --output pubkey.pub

# 3. Download the base Debian sid image
make download

# 4. Build a desktop + IME (first build takes a while)
make gnome-ibus-mozc

# 5. Start it as a VM (needs the libvirt daemon, qemu:///system)
./scripts/make-virsh-image.sh virt-gnome-ibus-mozc /tmp/unstable-gnome-ibus-mozc.workspace.qcow2
```

Log in as `debian` (password `debian`) and press **Ctrl + Space** (**Shift + Space**) to start
typing Japanese. The VM is registered in libvirt, so you can manage it with
`virsh` or `virt-manager` - handy for opening the SPICE console or restarting
the machine after a test.

## Status

The project is still in the **proof-of-concept** phase, and it is developed
mainly to test Mozc and other IMEs across desktops and input frameworks.

If you regularly test Japanese IMEs - give it a try.
