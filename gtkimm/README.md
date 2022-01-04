# GTK Input Methods Modules

This shared module was added as a stopgap, intended to allow using an IME framework with Chromium's
Ozone Wayland backend, as since the 97 release, [there's support for GTK4 IM modules](https://chromium.googlesource.com/chromium/src/+/23978dee2f47d915f79f2646822145aa021ad5a4).  
The Freedesktop runtime 21.08 release does not ship GTK4, so if the app's maintainer prefers not to
switch to the Gnome runtime, then building and packaging GTK4 and its IM modules with the app cannot
be avoided.  

The GTK3 IM modules are also enabled here in order to also ship updated GTK3 modules.

In order for GTK find the modules and dynamically load them, add `--env=GTK_PATH=/app/lib/gtkmodules` to 
the `finish-args` array.

The application should launched with the `--gtk-version=4` command-line flag to use GTK4.
