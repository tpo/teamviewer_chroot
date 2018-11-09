What's this?
------------

This script will launch [Teamviewer](http://teamviewer.com)
in a chroot with the same user that launched the script.

It has been tested with a Debian "jessie" chroot and with
Teamviewer 13, 64bit.

The script does a few fancy things:

* it bind mounts respectively copies the following directories
  and files outside the chroot to the inside:

  * /dev
  * /tmp
  * ~/.pulse
  * ~/.pulse/.pulse-cookie
  * /var/lib/dbus
  * $XDG_RUNTIME_DIR
  * /etc/resolv.conf

so that these facilities are available to teamviewer.

Setup
-----

The variable CHROOT needs to contain the path to
the chroot where teamviewer should be run.

Instead of setting it manually, you can also set it
in ~/.teamviewer_chroot.

Prerequisites
-------------

* you'll need to install teamviewer inside the chroot
* you need to have the same user name and UID inside chroot
* you need to copy `start_teamviewerd` and `stop_teamviewerd`
  to `$CHROOT/usr/local/bin`
