# vdu-8x16-psf
VDU is the Cyrillic screen &amp; keyboard driver developed by Oleg V.Baranovskiy with English/Ukrainian layouts.

I have used VDU for many years in MS-DOS and IBM OS/2 (DOS session). Later, after the Linux era came, I extracted the font from VDU driver and used it as a separate console font in Linux and BSD systems.

Files
=====

* vdu.com - VDU driver MS-DOS execurable file
* l30.com - 80x30 mode MS-DOS execurable file
* vdu-25.png - an initial screen after the VDU driver execution in MS-DOS (80x25 mode)
* vdu-30.png - an initial screen after the VDU driver execution in MS-DOS (80x30 mode)
* vdu.txt - TEXT format for all symbols
* vdu-glyph.png - a glyph file (all symbols on the same page)
* vdu.8x16.raw - font in RAW format
* vdu.8x16.psf - font in PSF1 format
* vdu.8x16.psf2 - font in PSF2 format


MS-DOS
======

Just execute `vdu.com` from command line or from `c:\autoexec.bat` to make it working.

To make sure that VDU driver is loaded in High memory, use `LH` in front of the command:

```
LH C:\UTILS\VDU.COM
```

Check the location of the driver with `mem /c/p` command.

In case, you want to switch to 80x30 mode, use `l30.com` utility before VDU execution:

```
LH C:\UTILS\L30.COM
LH C:\UTILS\VDU.COM
```

Linux
=====

Use `setfont` command to apply VDU console font:

```
setfont /usr/share/consolefonts/vdu.8x16.raw
```

BSD
===

I used this scenario to change the console font in NetBSD:

```
wsfontload -N vdu /usr/share/wscons/fonts/vdu.8x16.raw
wsconsctl -dw font=vdu
```

Good luck!

