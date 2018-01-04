do not use, in the process of revision

LineageOS For Micromax Q415
=============================

Initializing:

First, create a folder to hold the source code: 

	mkdir ~/lineage14

Next, naviate into that new directory via the terminal:

	cd ~/lineage14

To initialize your local repository use this command:

	repo init -u git://github.com/LineageOS/android.git -b cm-14.1

Also add the local manifests:

	git clone https://github.com/azzazza/local_manifest -b LoS-14.1 .repo/local_manifests

Then sync up with this command:

	repo sync --force-sync
	
You can make the 4 higher depending on how fast your internet connection is. 

Also add the prebuilt:

	git clone https://github.com/azzazza/prebuilt -b master vendor/cm

	git clone https://github.com/azzazza/opt -b master frameworks

-------------
 
_Building from source_
---------------

First:

	cd ~/lineage14

Second:

	. build/envsetup.sh
	brunch Q415
	
