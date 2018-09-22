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

### Fedora (Gnome 3)

Pros:
* Scaling is good. Pretty nice interface out of the box.

Cons:
* Netflix doesn't work.

## Native Citrix receiver

The Native Citrix receiver has some issues related with HiDPI displays. I got the receiver working on Linux Mint (Cinnamon), but the resolution was way off. The Windows client seems to have some options to scale the desktop, but apparently that option is not available on Linux.

One guy suggest running the Citrix receiver via VirtualBox. See https://plutonsblog.wordpress.com/2017/01/22/citrix-receiver-on-a-4k-hidpi-laptop/.

The remote desktop via HTML5 seems to work fine. Using Skype for 
business doesn't work.# Setup Manjaro

### Solution 1

Use HTML5 version of Citrix instead.

In order to prevent most shortcuts to be caught by the browser, I 
installed Opera browser, and disabled all shortcuts in the browser 
config.

## Make touch screen work in Firefox

### Solution 1

Found this solution elsewhere: if I start firefox from the command line with

env MOZ_USE_XINPUT2=1 firefox

### Solution 2

This worked for me (firefox 57.0.4, Arch Linux):

    open about:config in firefox to set dom.w3c_touch_events.enabled=1 (default is 2).

    edit /etc/security/pam_env.conf and add MOZ_USE_XINPUT2 DEFAULT=1

    reboot and restart firefox

## Right click on touch pad not working

Just solved it (for me at least stuck_out_tongue) it was gnome, in dconf: org.gnome.desktop.peripherals.touchpad click-method 'fingers' need to be: org.gnome.desktop.peripherals.touchpad click-method 'areas' 

## Git completing in bash

Just install 'bash-completion' from the Manjaro repos.
