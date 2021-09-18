# SAMSUNG Galaxy J5 | Build Instructions with Manifest
<br/>

Set up Linux environment
```
wget https://github.com/daviiid99/LineageOS_J5-2015/blob/Manifest/environment.sh 
sh ./environment.sh
```
<br/>

Initialize LineageOS repo:
```
mkdir -p ~/android/lineage
cd ~/android/lineage
repo init https://github.com/daviiid99/sept.git -b android
```
<br/>

Download latest manifest:
```
mkdir -p .repo/local_manifests
curl https://raw.githubusercontent.com/daviiid99/LineageOS_J5-2015/Manifest/j5.xml > .repo/local_manifests/j5.xml
curl https://raw.githubusercontent.com/daviiid99/LineageOS_J5-2015/Manifest/gapps.xml > .repo/local_manifests/gapps.xml
```
<br/>

Sync repo:
```
repo sync
source build/envsetup.sh
```
<br/>

OpenGApps configure source
```
sudo apt install git-lfs
git lfs install
repo forall -c git lfs pull
rm modules/TrichromeLibrary/Android.mk # This is actually needed for Chrome arm
```
<br/>

Build:
```
brunch j5nlte #for SM-J500FN
brunch j5lte #for SM-J500F/G/M/NO/Y
brunch j5ltechn #for SM-J5008
brunch j53gxx #for SM-J500H
```

<br/>
