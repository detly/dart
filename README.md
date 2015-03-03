# Dart

A hybrid Kali/Debian Wheezy distribution.

Note that this only works under live-build 4 at the moment.

## Note about live-build

In order to work around [bug #773833](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=773833) you need to patch `/usr/lib/live/build/binary_hdd`. That is
actually the file on the machine running live-build, not the chroot.

## Configuration

The image can be customised using this following environment variables when
calling `lb config`:

`DART_APT_CACHE`: To use eg. `apt-cacher-ng`, set `DART_APT_CACHE` to the server
and protocol of the cache, eg `192.168.1.100:3142`. Note that even if your cache
can be resolved via Avahi or Samba, certain stages of `live-build` will not be
able to use those services for resolution. This defaults to an empty value.

`DART_HOSTNAME`: The hostname of the live system. Defaults to `dart`.

`DART_USERNAME`: The username of the live system. Note that the password will
still be `live`. Defaults to `user`.
