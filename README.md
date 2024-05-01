## Project Blaze GSI  
This is an unofficial build.  

## Getting Started:

Create a new working directory for your Project Blaze build and navigate to it:
```
mkdir blaze; cd blaze
```

Initializing a local repository and adding manifests:
```
repo init --depth=1 -u https://github.com/ProjectBlaze/manifest -b 14-QPR2
git clone https://github.com/j7b3y/treble_pb .repo/local_manifests -b 14-QPR2-WIP
```

Then to sync up:
```
repo sync -c --force-sync --optimized-fetch --no-tags --no-clone-bundle --prune
```

Apply patch:
```
git clone https://github.com/j7b3y/blaze_patches_unified -b 14-QPR2-WIP
bash ./blaze_patches_unified/apply-patchers.sh blaze_patches_unified

```

Build:
```
. build/envsetup.sh
lunch blaze_treble_arm64_vN-userdebug # or blaze_treble_arm64_gN-userdebug
WITHOUT_CHECK_API=true make systemimage
```  

## Thanks  

- [ProjectBlaze](https://github.com/ProjectBlaze)
- [phhusson](https://github.com/phhusson/)
- [TrebleDroid](https://github.com/TrebleDroid)