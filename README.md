# HOW-TO Build
* Initialize the repository
   
   ```sh
   repo init -u git://github.com/LineageOS/android.git -b cm-13.0
* Add my manifest to the .repo/local_manifests folder
   
   
   ```sh
   cp local_manifest.xml .repo/local_manifests
* Sync latest LineageOS 13.0 sources
  
  
  ```sh
   repo sync -j20 --force-sync
* Apply all Patches
   
   
   ```sh
   patch -p1 < device/samsung/i959/patch/PATCH
* You are good to go, proceed with the compiling process
OPTIONAL (if you want built-in root support):
   
   
   ```sh
   export WITH_SU=true

