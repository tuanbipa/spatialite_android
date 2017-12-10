	Copyright (C) U.S. Army Geospatial Center <http://www.agc.army.mil/>

	This file is based on the work at <http://code.google.com/p/spatialite-android/> 
	with the code license <http://www.gnu.org/licenses/lgpl.html>. 

    This file is part of spatialite-android.

    spatialite-android is free software: you can redistribute it and/or modify
    it under the terms of the GNU Lesser General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    spatialite-android is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU Lesser General Public License for more details.

    You should have received a copy of the GNU Lesser General Public License
    along with spatialite-android.  If not, see <http://www.gnu.org/licenses/>.

Steps:
0. mkdir scratch && cd scratch
1. git clone https://code.google.com/p/spatialite-android/
2. cd spatialite-android/spatialite-android-library/jni
3. wget http://download.osgeo.org/geos/geos-3.2.2.tar.bz2
4. wget ftp://ftp.remotesensing.org/proj/proj-4.7.0.tar.gz
5. tar xvjf geos-3.2.2.tar.bz2
6. tar xvzf proj-4.7.0.tar.gz
7. cd proj-4.7.0
8. ./configure --build=x86_64-pc-linux-gnu --host=arm-linux-eabi
9. cd ../geos-3.2.2
10. ./configure --build=x86_64-pc-linux-gnu --host=arm-linux-eabi
11. vi source/headers/geos/platform.h
    Add this new line anywhere:
    #define HAVE_ISNAN 1
12. cd ..
13. export PATH=$PATH:~kirkj/apps/android-sdk-macosx/platform-tools:~kirkj/apps/android-sdk-macosx/tools:~kirkj/apps/android-ndk-r7c
14. ndk-build

15. cd geos-3.2.2
16. make clean
16. cd ..
17. cd proj-4.7.0
18. make clean
19. cd ..
20. rm proj-4.7.0.tar.gz 
21. rm geos-3.2.2.tar.bz2 

22. to reduce the size of the zip package, optionally remove the "obj" folder contents.

