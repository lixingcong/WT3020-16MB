# WT3020-16MB

NEXX WT3020 16MB flash patch for OpenWrt

Usage:

```
cd openwrt
patch -p1 < xxx.patch
```

Build and flash your openwrt image to device.

It will take 5 minutes to resize the partition on the first boot. The LED keep blinking.

If your execute ```df -h``` during the resize operation, it will output the wrong size(28MB):

```
root@OpenWrt:~# df -h
Filesystem                Size      Used Available Use% Mounted on
/dev/root                 3.8M      3.8M         0 100% /rom
tmpfs                    28.1M    228.0K     27.9M   1% /tmp
tmpfs                    28.1M     52.0K     28.1M   0% /tmp/root
overlayfs:/tmp/root      28.1M     52.0K     28.1M   0% /
tmpfs                   512.0K         0    512.0K   0% /dev
```

When the resize operation is done, the LED stop blinking and ```df``` result is

```
root@OpenWrt:~# df -h
Filesystem                Size      Used Available Use% Mounted on
/dev/root                 3.8M      3.8M         0 100% /rom
tmpfs                    28.1M    228.0K     27.9M   1% /tmp
tmpfs                    28.1M     52.0K     28.1M   0% /tmp/root
tmpfs                   512.0K         0    512.0K   0% /dev
/dev/mtdblock6           10.1M    520.0K      9.6M   5% /overlay
overlayfs:/overlay       10.1M    520.0K      9.6M   5% /
```

# Refer

https://github.com/denisandroid/WT3020-PatchMB


