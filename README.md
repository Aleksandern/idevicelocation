About
=====
The idevicelocation tool allows to set the location on iOS Devices. The devices can be connected via USB or WiFi.
It makes use of the fabulous libimobiledevice library that allows communication
with iOS devices.

Requirements
============

Development Packages of:

	libimobiledevice
	libusbmuxd
	libplist
	openssl

Software:

	usbmuxd
	make
	autoheader
	automake
	autoconf
	libtool
	pkg-config
	gcc

Installation
============

To compile run:

	./autogen.sh
	make
	sudo make install

Usage
=====

	$ idevicelocation [OPTIONS] LATITUDE LONGITUDE
 
Set the location passing two arguments, latitude and longitude:

	$ idevicelocation 48.856614 2.3522219000000177 

Passing negative values :

	$ idevicelocation 77.432332 -- -7.008373564
	
	$ idevicelocation -- -77.432332 -7.008373564

Stopping Location Simulation:

	$ idevicelocation --stop

Options:

	-d enable connection debug messages.
	-u specify device UDID.
	-h help.
	-s stop location simulation on device. 
	
Troubleshooting
===============

Mac Users: 

	If the compiler cant find the openssl libs try this:

		export PATH=/usr/local/opt/openssl/bin:$PATH
		export LD_LIBRARY_PATH=/usr/local/opt/openssl/lib:$LD_LIBRARY_PATH
		export CPATH=/usr/local/opt/openssl/include:$CPATH
		export LIBRARY_PATH=/usr/local/opt/openssl/lib:$LIBRARY_PATH
		export PKG_CONFIG_PATH=/usr/local/opt/openssl/lib/pkgconfig


