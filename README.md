# Show Me GSI

[Generic System Image](https://source.android.com/setup/build/gsi) optimized for Sony and Xiaomi devices. Currently tested:

- Sony Xperi XZ2 (akari)
- Xiaomi Redmi Note 9 Pro (joyeuse)

Other devices should work, including:

- Xiaomi Redmi Note 9S (curtana)

## Downloads

Ensure your device has the latest factory image and is unlocked with the following tools:

### Sony

- [Sony Flash Tool](https://developer.sony.com/develop/open-devices/get-started/flash-tool)

### Xiaomi
- [Xiaomi Flash Tool](https://www.xiaomiflash.com/)
- [Xiaomi Stock ROMs](https://c.mi.com/oc/miuidownload/)
- [Xiaomi Fastboot Restore](https://c.mi.com/oc/miuidownload/detail?guide=2)

## Build Box

```
apt-get -y install --no-install-recommends \
    bison \
    flex \
    gcc-multilib \
    g++-multilib \
    libncurses5 \
    libxml2-utils \
    python-is-python3 \
    zip \
    zlib1g-dev
```

### Initialize

```
repo init -u https://android.googlesource.com/platform/manifest -b android-10.0.0_r36
git clone git@github.com:ShowMeGSI/manifests.git .repo/local_manifests
repo sync
```

### Build
. build/envsetup.sh
lunch
make -j8
