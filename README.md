# Tanix X4 local manifest

Additional repositories for building LineageOS 24.0 on the Tanix X4 (Amlogic S905X4).

## Initialize and sync

Start in an empty source directory with the Android build dependencies and `repo` installed:

```sh
repo init -u https://github.com/LineageOS/android.git -b lineage-24.0 --git-lfs
git clone -b lineage-24.0 https://github.com/tanix-x4-los/manifest.git .repo/local_manifests
repo sync -c
```

For an existing checkout, use this manifest instead of other local manifests defining the same Amlogic projects. Duplicate project paths will cause `repo` to fail.

## Build

```sh
source build/envsetup.sh
breakfast x4
m bacon
```

The manifest includes the device and proprietary vendor trees, Amlogic common trees, the kernel 5.15 build dependencies, X4 kernel configuration and board drivers, GPU/media modules, and W1 Wi-Fi/Bluetooth modules.

U-Boot is maintained separately in [tanix-x4-los/u-boot](https://github.com/tanix-x4-los/u-boot). It is not built or flashed by these instructions.

Google apps are not included. Uncommitted local changes are not distributed by this manifest.
