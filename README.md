Resurrection Remix OS For Micromax Q415
=============================

Initializing:

First, create a folder to hold the source code: 

	mkdir ~/RR

Next, naviate into that new directory via the terminal:

	cd ~/RR

To initialize your local repository use this command:

	repo init -u https://github.com/ResurrectionRemix/platform_manifest.git -b nougat

Also add the local manifests:

	git clone https://github.com/azzazza/local_manifest -b RR .repo/local_manifests

Then sync up with this command:

	repo sync -j4 -f --no-clone-bundle --no-tags --force-sync
	
You can make the 4 higher depending on how fast your internet connection is. 

Also add the prebuilt:

	mkdir prepare
	
	git clone https://github.com/azzazza/prebuilt -b master prepare/vendor/cm
	
	git clone https://github.com/azzazza/opt -b master prepare/frameworks
	
	cp -R prepare/vendor/cm/prebuilt/ vendor/cm/
	
	cp -R prepare/frameworks/opt/ frameworks/
	
or script

#!/bin/bash

mkdir ~/RR

cd ~/RR

repo init -u https://github.com/ResurrectionRemix/platform_manifest.git -b nougat

git clone https://github.com/azzazza/local_manifest -b RR .repo/local_manifests

repo sync -j4 -f --no-clone-bundle --no-tags --force-sync

mkdir prepare

git clone https://github.com/azzazza/prebuilt -b master prepare/vendor/cm

git clone https://github.com/azzazza/opt -b master prepare/frameworks

cp -R prepare/vendor/cm/prebuilt/ vendor/cm/

cp -R prepare/frameworks/opt/ frameworks/

-------------
 
_Building from source_
---------------

First:

	cd ~/RR

Second:

	. build/envsetup.sh && export WITH_SU=true && brunch Q415
	
