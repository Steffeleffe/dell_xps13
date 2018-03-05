# Linux on a Dell XPS 13 (touch screen)

This is my guide on how I have set up my Dell XPS 13 (9350).

## What Linux distro to choose?

After booting a few distros up via USB stick, I realized that most desktop environments don't like the HiDPI display on the XPS 13 (resolution is QHD+ at 3200x1800).

### Linux Mint (Cinnamon)

Pros:
* Scales perfectly out of the box.

Cons:
* Cannot make it play Netflix. Tried both Firefox and Chromium, enabling DRM, switching "user agent"... nothing worked.

### Manjaro (Gnome 3)

Latest Ubuntu has Gnome 3.26 which should handle HiDPI okay as well.

Pros:
* Scales perfectly out of the box.
* Netflix works out of the box on Firefox.


## Native Citrix receiver

The Native Citrix receiver has some issues related with HiDPI displays. I got the receiver working on Linux Mint (Cinnamon), but the resolution was way off. The Windows client seems to have some options to scale the desktop, but apparently that option is not available on Linux.

One guy suggest running the Citrix receiver via VirtualBox. See https://plutonsblog.wordpress.com/2017/01/22/citrix-receiver-on-a-4k-hidpi-laptop/.

The remote desktop via HTML5 seems to work fine.
