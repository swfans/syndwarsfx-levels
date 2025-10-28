# syndwarsfx-levels

Map and level files for Syndicate Wars Fan Expansion.

## About

**Syndicate Wars Fan Expansion**, alternative binary for the classic Bullfrog game.

Alongside fixes to the game executable code, an updated set of assets is
required to use the full potential of the code fixes.

This repository contains the original maps and levels developed by
Bullfrog, with additional fixes applied to the files by fan community.

## Installation from a release

Download the release `syndwarsfx-levels-*.zip` file. Copy the extracted
`LEVELS` and `MAPS` folders to a previous SyndWarsFX installation,
replacing the existing files.

### General building instructions

To build **Syndicate Wars Levels**, use the following steps:

1. go into the directory with `syndwarsfx-levels` source release
2. do `autoreconf -if` to create build scripts from templates
3. do `./configure` to make the build scripts find required dependencies
4. do `make` to build release versions of data files
5. do `make install` to copy the files into `syndwarsfx` installation folder

You should now have the latest maps and levels on your installation folder.

### Building not really required

Note that at the moment no files are really built, they are just copied.
So while this will change at some point, currently just copying the files
from source release would work as well.

#### Build example - Ubuntu 20.04 64-bit

Here are specific commands required to build the levels on Ubuntu linux.

Download the `syndwarsfx-levels` source release, and extract it somewhere.
Go to that folder, and generate build scripts from templates using autotools:

```
autoreconf -ivf
```

Next, proceed with the build steps; we will do that in a separate folder.

```
mkdir -p release; cd release
../configure
make V=1
```

The `V=1` variable makes `make` print each command it executes, which makes
diagnosing issues easier.

You can use `make install` to add the files to your installation, or copy
them to a new folder from which you may copy them manually.

To copy output files to a `pkg` folder, creating  proper sub-folders for
release, use:


```
make V=1 DESTDIR=$PWD/pkg install
```

That's it, now you have the leval and map files ready.

## Done

That's all. See more documentation in [SyndWarsFX repo](https://github.com/mefistotelis/syndwarsfx).
