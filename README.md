A fork of [go-astilectron](https://github.com/asticode/go-astilectron) that makes the minimal amount of changes required to get it working under [FreeBSD](https://www.freebsd.org/) for my projects. Everything documented there still applies to this except for automatic downloading of the zip files not being supported on FreeBSD. If you don't intend on targetting FreeBSD, then I recommend you use the original as this will most likely be slightly out of date, though I do intend to pull changes from the original every so often. If you are interested in this, I don't support automatically downloading the FreeBSD version because 1) the build of electron I use for FreeBSD only provides pkg files (so I would need to host zip files) and 2) I embed the electron zip files in my application binaries (currently using [vfsgen](https://github.com/shurcooL/vfsgen), but I am by no means married to it as a solution).

If you want to run astilectron on FreeBSD, you can also do it without this:

1) In astilectron.go, add freebsd to the validOSes map.

2) In paths.go, add freebsd's binary path to the initAppExecutable function. If you package it the same way I do, it's the same as Linux.

The above is basically all that has been changed (I also added a panic when trying to download the FreeBSD version automatically as, once again, that's not supported). If you do the above, you should have a functional astilectron build on your FreeBSD system assuming you've got embedding setup properly. 
