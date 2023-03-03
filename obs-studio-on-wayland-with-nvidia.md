# obs-studio-on-wayland-with-nvidia

---
tags:
  - obsstudio
  - wayland
  - nvidia
---

## Problem

Using OBS Studio with Wayland can be an issue. You cannot use NVENC
because you need to set an environmental variable and also
you have to edit udev rules to enable.

There is a chance that you want to set `__NV_PRIME_RENDER_OFFLOAD` to `1`
so that you can use NVIDIA on Wayland.

However, this causes some weird behavior to OBS Studio such as
Pipewire giving you black screen on Screen Capture.

## Solutions

Following all of these may fix your issues:

- Enabling Hardware Acceleration as described in the ArchWiki [https://wiki.archlinux.org/title/NVIDIA#Hardware_accelerated_video_decoding](https://wiki.archlinux.org/title/NVIDIA#Hardware_accelerated_video_decoding)
- Add the following to your `/etc/X11/xorg.conf.d` as `10-nvidia-drm-output-class.conf`:

```
Section "OutputClass"
    Identifier "intel"
    MatchDriver "i915"
    Driver "modesetting"
EndSection

Section "OutputClass"
    Identifier "nvidia"
    MatchDriver "nvidia-drm"
    Driver "nvidia"
    Option "AllowEmptyInitialConfiguration"
    Option "PrimaryGPU" "yes"
    ModulePath "/usr/lib/nvidia/xorg"
    ModulePath "/usr/lib/xorg/modules"
EndSection
```

Then enable NVIDIA modesetting by following [https://en.opensuse.org/SDB:NVIDIA_the_hard_way#Enabling_NVIDIA_modesetting](https://en.opensuse.org/SDB:NVIDIA_the_hard_way#Enabling_NVIDIA_modesetting). Reboot.

- For the issue where setting `__NV_PRIME_RENDER_OFFLOAD=1` can cause black screen recording, create a wrapper script for OBS by setting it to `0`.
  If using flatpak OBS Studio, you can just use the commandline to modify env vars or use Flatseal for that.

**DISCLAIMER**

These solutions are in no way 100% guaranteed to work. Results may vary from user to user, computer to computer.



