# Manifest for building CrDroid 12.1 for gtaxlwifi, gtaxllte, gtanotexlwifi, and gtanotexllte

`gtaxlwifi` is the codename for the WiFi-only variant of the Samsung Galaxy Tab A 10.1" (2016), with model SM-T580.

`gtaxllte` is the codename for the LTE variant of the Samsung Galaxy Tab A 10.1" (2016), with model SM-T585, and also with SM-T585N0 and SM-T585C for Korea and China respectively.

`gtanotexlwifi` is the codename for the WiFi-only variant of the Samsung Galaxy Tab A 10.1" (2016) **with S-Pen**, with model SM-P580, and also with SM-P583 for China.

`gtanotexllte` is the codename for the LTE variant of the Samsung Galaxy Tab A 10.1" (2016) **with S-Pen**, with models SM-P585, SM-P585M, SM-P585Y, SM-P585N0, and SM-P588C.

Some extremely basic instructions:
- Make a new directory for LineageOS sources and enter it:
```
mkdir crdroid-12.1
cd crdroid-12.1
```

- Initialize repo in this directory with the CrDroid 12.1 android repository:
```
repo init -u https://github.com/crdroidandroid/android.git -b 12.1 --git-lfs
```

- Clone this repository to .repo/local_manifests for roomservice.xml containing the repositories needed to build for these devices:
```
git clone https://github.com/mrx7014/gtaxl-manifests.git -b crdroid-12.1 .repo/local_manifests
```

- Sync all of the repositories in manifests (including CrDroid manifests):
```
repo sync --force-sync --no-tags --no-clone-bundle -c
```

- Finally, build as you like.
```
. build/envsetup.sh
lunch lineage_<device_codename>-userdebug
brunch <device_codename>
```
