Patches are applied from https://github.com/denisandroid/WT3020-PatchMB

But mkporayfw.c is [no longer available](https://forum.openwrt.org/t/mkporayfw-c-no-longer-avail-in-22-03-0/138140) in openwrt branch 22.03

The patch of mkporayfw.c is produced by these steps:

```
cd /tmp
git clone https://git.openwrt.org/project/firmware-utils.git
cd firmware-utils

# the git hash 'COMMIT_HASH' is located in tools/firmware-utils/Makefile
git checkout COMMIT_HASH

# Apply the old patches
patch -p1 < /path/to/openwrt/openwrt/tools/firmware-utils/patches/*.patch
git add *

# edit mkporayfw.c .....

# Produce the new patch, 'XXX' is next number of patch
git diff > /path/to/openwrt/openwrt/tools/firmware-utils/patches/XXX-wt3020-16m.patch
```
