## Project Blaze GSI  
This is an unofficial build.  

## Getting Started:

Create a new working directory for your Project Blaze build and navigate to it:
```
mkdir blaze; cd blaze
```

Initializing a local repository and adding manifests:
```
repo init -u https://github.com/ProjectBlaze/manifest.git -b 12.1
git clone https://github.com/j7b3y/treble_pb .repo/local_manifests -b android-12.1
```

Then to sync up:
```
repo sync -c --force-sync --optimized-fetch --no-tags --no-clone-bundle --prune
```

Apply patch:
```
git clone https://github.com/j7b3y/blaze_patches_unified -b blaze-12.0
bash ./blaze_patches_unified/apply-patchers.sh blaze_patches_unified

```

Generating mk:
```
cd device/phh/treble
bash generate.sh blaze
```

Build:
```
. build/envsetup.sh
lunch treble_arm64_bvN-userdebug
WITHOUT_CHECK_API=true make systemimage
```  

## Thanks  

- [ProjectBlaze](https://github.com/ProjectBlaze)
- [phhusson](https://github.com/phhusson/)
- [AndyCGYan](https://github.com/AndyCGYan)
- [ponces](https://github.com/ponces/)
