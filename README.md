# Sony GSI

[Generic System Image](https://source.android.com/setup/build/gsi) optimized for Sony devices. Currently tested:

- Sony Xperia 10 ii (pdx201)

## Downloads

Ensure your device has the latest factory image and is unlocked with the following tools:

- [Sony Flash Tool](https://developer.sony.com/develop/open-devices/get-started/flash-tool)

## Build Box

```sh
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

```sh
repo init -u https://android.googlesource.com/platform/manifest -b android-10.0.0_r41
git clone -b android-10.0.0_r41 git@github.com:SonyGSI/manifests.git .repo/local_manifests
repo sync
```

### Build

```sh
. build/envsetup.sh
lunch
make -j8
```
