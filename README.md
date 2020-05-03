AVSRepo (Avisynth Repository)
======

(fork of VSRepo https://github.com/vapoursynth/vsrepo)

A simple package repository for Avisynth. It is implemented in a way that
keeps no state between invocations and can therefore be pointed at any
pre-existing plugin and script directory.

By default binaries matching the platform Python is running on are installed.
This can be overridden by adding `-t win32` or `-t win64` to the commandline.

Usage
-----

Install plugins and scripts. Identifier, namespace, modulename and name
are searched for matches in that order.
```
avsrepo.py install havsfunc ffms2 d2v
```

Update all installed packages to the latest version.
```
avsrepo.py upgrade-all
```

Fetch latest package definitions.
```
avsrepo.py update
```

List all currently installed packages.
```
avsrepo.py installed
```

List all known packages. Useful if you can't remember the namespace or
identifier.
```
avsrepo.py available
```

Remove all files related to a package. Dependencies are not taken into
consideration so uninstalling plugins may break scripts.
```
avsrepo.py uninstall nnedi3
```


Updating the Repository
---------

avsupdaterepo.py has two main purposes. The `compile` command which combines all
the individual package files into one distributable file and `update-local`
which queries the github api and tries to automatically add all new releases.

It's only useful if you want to update or add new packages.

Usage example:
```
avsupdaterepo.py update-local -o -g <github token>
avsupdaterepo.py compile
```
