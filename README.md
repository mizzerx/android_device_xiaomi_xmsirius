android_device_xiaomi_xmsirius
For building TWRP for Xiaomi Mi 8 SE

TWRP device tree for Xiaomi MI 8 SE

Features
Works:

ADB
Decryption of /data
Screen brightness settings
Vibration on touch
Correct screenshot color
Compile
First checkout minimal twrp with omnirom tree:

repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0
repo sync
Then add these projects to .repo/manifest.xml:

<project path="device/xiaomi/xmsirius" name="mizzerx/android_device_xiaomi_xmsirius" remote="github" revision="android-9.0" />
Finally execute these:

. build/envsetup.sh
lunch omni_xmsirius-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
To test it:

fastboot boot out/target/product/xmsirius/recovery.img
Contributors
Here

Other Sources
Kernel Sources: https://github.com/solidv/kernel_xiaomi_sdm710

Thanks
Thanks to @notsyncing for the base: https://github.com/notsyncing/android_device_xiaomi_polaris