Introduction
============

This script updates CloudFlare A records using their v4 API.

The script is intended to be used with [networkd-dispatcher](https://gitlab.com/craftyguy/networkd-dispatcher).

Configuration
============

You will need a valid CloudFlare login.

Set values as appropriate in `ddns.config` (or `/etc/cloudflare-ddns.conf`)


Arch and Arch-based Users
-------------------------

A PKGBUILD is provided for your convenience.

Other networkd-dispatch users
-----------------------------

1) Place `ddns-start` and `ddns.config` in the same folder in /etc/networkd-dispatcher/routable.d/
2) Set values in `ddns.config`
