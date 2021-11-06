# Guide For Building Roms for gsi
This guide assumes you are running ubuntu 21.04 (any version above 20.04 should be fine)
It is recommended to have 16gb ram or more for building and at least 100gb of storage (200gb+ recommended for faster building)
#This guide also assumes that you have all android depencies already installed !!!

Step 1: Start by making a folder to work on, run: mkdir gsibuild;cd gsibuild

Step 2: Now we need to initiate the repo of the rom you are building, Find your rom's manifest (Search "RomName manifest" on any search engine and find the github or gitlab page) You will need the repo command for the rom, It's usually gonna be something like: repo init -u https://github.com/ROMNAME/android_manifest.git -b 12.0 (Do not use this command, find the correct command for your rom) (Select the correct branch for the android version you are building at the top of the page)

Step 3: After Repo has initiated you need to download the local manifest's, Run: cd .repo;mkdir local_manifests;git clone --single-branch https://github.com/phhusson/treble_manifest.git -b android-12.0 .repo/local_manifests

Note: If Building android 11 run: git clone --single-branch https://github.com/phhusson/treble_manifest.git -b android-11.0 .repo/local_manifests

Step 4: Downloading the rom source code, we already initiated the repo earlier so we just need to sync it (download it) This Will Take a long time depending on your internet connection (This is 90-100gb+ Of data!) Run: repo sync -j$(nproc --all)
