AEX OS For Micromax Q415
=============================

Initializing:

First, create a folder to hold the source code: 

	mkdir ~/AEX

Next, naviate into that new directory via the terminal:

	cd ~/AEX

To initialize your local repository use this command:

	repo init -u git://github.com/AospExtended/manifest.git -b 7.x

Also add the local manifests:

	git clone https://github.com/azzazza/local_manifest -b AEX .repo/local_manifests

Then sync up with this command:

	repo sync -j4 -f --no-clone-bundle --no-tags --force-sync
	
You can make the 4 higher depending on how fast your internet connection is. 

Also add the prebuilt:

	mkdir prepare
	
	git clone https://github.com/azzazza/prebuilt -b master prepare/vendor/aosp
	
	git clone https://github.com/azzazza/opt -b master prepare/frameworks
	
	cp -R prepare/vendor/aosp/prebuilt/ vendor/aosp/
	
	cp -R prepare/frameworks/opt/ frameworks/
	
or script

#!/bin/bash

mkdir ~/AEX

cd ~/AEX

repo init -u git://github.com/AospExtended/manifest.git -b 7.x

git clone https://github.com/azzazza/local_manifest -b AEX .repo/local_manifests

repo sync -j4 -f --no-clone-bundle --no-tags --force-sync

mkdir prepare

git clone https://github.com/azzazza/prebuilt -b master prepare/vendor/aosp

git clone https://github.com/azzazza/opt -b master prepare/frameworks

cp -R prepare/vendor/aosp/prebuilt/ vendor/aosp/

cp -R prepare/frameworks/opt/ frameworks/

-------------
 
_Building from source_
---------------

First:

	cd ~/AEX

Second:

	. build/envsetup.sh && lunch aosp_Q415-userdebug && mka aex
	
