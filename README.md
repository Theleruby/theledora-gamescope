# theledora-gamescope

Theledora is a customized version of Fedora Atomic Desktop 43. It is based on Bazzite, a fork of Fedora Kinoite tailored towards gamers.

The purpose of Theledora is to allow me to preinstall things from the Fedora package repositories which cannot be installed via flatpak, or which I found work better from the package repository. This avoids having to layer the packages using rpm-ostree, which is prone to breaking with package conflicts. Installing some of those packages also avoids me having to use containers for most of the stuff that I do (not everything, but that's OK).

## Available images

| Variant | Purpose | Compatible GPU | Desktop environment | Gamescope session |
|--|--|--|--|--|
| [theledora-nvidia-open](https://github.com/Theleruby/theledora-nvidia-open) | Desktop PC | NVIDIA GPU<br/>(1600 series or later) | KDE Plasma | No |
| [theledora-gamescope](https://github.com/Theleruby/theledora-gamescope) | Handheld or HTPC | AMD GPU<br/>(RX 400 series or later) | KDE Plasma | Yes |

## About this image

This image (**theledora-gamescope**) is based on [bazzite-deck:stable-43](https://github.com/ublue-os/bazzite/pkgs/container/bazzite-deck). It is intended for handhelds and home theater PCs which have AMD GPUs (RX 400 series or later). It behaves roughly like the Steam Deck, booting into a gamescope session (Steam Gaming Mode) by default, with a KDE Plasma desktop session being available for system maintenance tasks. If you own a Steam Deck then the experience should be very close to what you're used to already.

If being used for a home theater PC, it is best paired with the new Steam Controller, although it works fine with various other types of controllers. When using a non-Steam controller, the options menu can be accessed by pressing Xbox+A or equivalent.

Intel and NVIDIA GPUs are not supported on this image. If you need to support an NVIDIA GPU then you should use the desktop image instead.

Note that when you're using the gamescope session it will claim you're running SteamOS despite this being inaccurate. This is due to limitations of the Steam Gaming Mode UI and can just be ignored.

## Legal notice and disclaimer

This is an experimental image which was created for my sole personal use only. I don't intend for anyone to use this except me, and I don't provide any support.

I don't consider Theledora to be its own operating system or distro - apart from the extra preinstalled packages, this bootc image is literally just of Bazzite. The customization of this image is similar to using NTLite to modify a Windows install.wim file, and was done solely to make my Atomic Desktop journey easier, being made necessary because of the particular way in which the Fedora Atomic Desktop works. All queries and legal notices which are not directly related to the customizations made to this image should therefore be directed towards Universal Blue, the Fedora Project and/or Red Hat (whichever is appropriate).

## Using the image

Install Bazzite-Deck from https://download.bazzite.gg/bazzite-deck-stable-live-amd64.iso

After installing, do `sudo bootc switch --enforce-container-sigpolicy ghcr.io/theleruby/theledora-gamescope:latest` and then reboot.

## Documentation

Bazzite Documentation: https://docs.bazzite.gg/

Fedora Atomic Desktops User Guide: https://docs.fedoraproject.org/en-US/atomic-desktops/

I also made a wiki to document various Linux stuff which might be useful: https://pengwings.theleruby.com/

## Making your own image

Take a look at https://github.com/ublue-os/image-template for instructions.
