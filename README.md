#HOW-TO Build

    Initialize the repository

repo init -u git://github.com/LineageOS/android.git -b cm-14.1

    Add my manifest to the .repo/local_manifests folder (don't worry about the alert you will get about being DEPRECATED)  

cp local_manifest.xml .repo/local_manifests

    Sync latest LineageOS 14.1 sources  

repo sync -j20 --force-sync

    Apply all Patches

./Exynos5410_patcher/patch.sh

    You are good to go, proceed with the compiling process OPTIONAL (if you want built-in root support):

export WITH_SU=true
export WITH_TWRP=true

copy these:
device/samsung/ja3gduosctc/configs/etc/spn-conf.xml
packages/apps/OTAUpdates

cd '/path/to/lineageos14.1'
patch -p1 < PATCH

cd '/path/to/lineageos14.1'
. build/envsetup.sh
brunch ja3gduosctc
jack-admin kill-server
