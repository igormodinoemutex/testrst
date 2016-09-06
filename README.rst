qm-dfu-util - Intel® Quark™ Microcontroller Device Firmware Upgrade Utility
###########################################################################

*qm-dfu-util* is a fork of |dfu-util|_, a host side implementation of the `DFU
1.0`_ and `DFU 1.1`_ specification of the USB forum.

DFU is intended to download and upload firmware to devices connected over USB.
It ranges from small devices like micro-controller boards up to mobile phones.
*qm-dfu-util* allows you to download firmware to your Intel® Quark™
Microcontroller by using the serial interface (UART).

Building
********
LINUX
=====
For building the host tool, first configure the build with:
::
	./autogen.sh
	./configure

Then compile it with:
::
	make

The generated binary is *src/dfu-util-qda* .
You can have it installed into your GNU/Linux host with:
::
	make install

and you'll find */usr/local/bin/dfu-util-qda*.

WINDOWS
=======
Windows Native with MSYS
========================
Windows binaries can be built in a MSYS2 environment. Download and istall it before compiling from http://msys2.github.io

Once installed, MSYS2 would have created a Linux-like environment in your Windows PC.

Copy the qm-dfu-util folder to *<MSYS2_installation_folder>\home\<your_user>*
Open MSYS2 Shell from your Windows Start Menu.
Install the needed components:
::
	pacman -S autoconf
	pacman -S perl
	pacman -S automake
	pacman -S make
	pacman -S mingw-w64-x86_64-gcc
	PATH=$PATH:/mingw64/bin/


For building the host tool, first configure the build with:
::
	./autogen.sh
	./configure

Then compile it with:
::
	make

The generated binary is *src/dfu-util-qda.exe*.


Windows Cross-compile from Ubuntu16
===================================
Before compiling, we'll need to install MinGW:
::
	sudo apt-get install mingw-w64

For building the host tool, first configure the build with:
::
	./autogen.sh
	./configure --host=x86_64-w64-mingw32

Then compile it with:
::
	make

The generated binary is *src/dfu-util-qda.exe*.

.. |dfu-util| replace:: *dfu-util*
.. _dfu-util: http://dfu-util.gnumonks.org
.. _`DFU 1.0`: http://www.usb.org/developers/devclass_docs/usbdfu10.pdf
.. _`DFU 1.1`: http://www.usb.org/developers/devclass_docs/DFU_1.1.pdf
