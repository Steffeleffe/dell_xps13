# Setup Manjaro

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
