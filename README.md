# aufs-dir-tools

A set of small Bash tools for managing files in the `aufs` union file system. Written for use on portable Linux distros.

Tested on:

* Porteus 5.01 and 5.1
* Puppy Linux S15Pup64 22.12

License: [GPL v3](https://www.gnu.org/licenses/gpl-3.0.en.html). **There is no warranty; you run these programs at your own risk.**

These tools were written and tested by hand. No GPT coding agents were used to produce any of the code or documentation.

## Requirements

* GNU Bash (tested on version 5.1.16)
* GNU coreutils (tested on version 9.5)
    * for Puppy Linux: the full `realpath` command must be installed. The `busybox` implementation is not sufficient.

## List of tools

* `aufs-find`: Find files by the number of versions they have.
* `aufs-list`: Find all the versions of one file in different overlaid branches.
* `aufs-clashes`: Find all file clashes between numbered branches.
* `aufs-diff`: Find the diff between any two versions (in different branches) of one file.
* `aufs-revert`: Delete the uppermost, writeable version of a file, without creating a whiteout.
* `aufs-unwh`: Remove whiteout deletion files for a path. 

For usage guidance on a tool, run it with the `-h` flag.

## Install

To build a module for use on Porteus:

```bash
git clone https://github.com/lcpterid/aufs-dir-tools.git
cd aufs-dir-tools
./build-porteus
```

then activate or move it.

## Limitations

* These tools work only if you have a single AUFS file system, with one set of branches. It must also be mounted at the root (`/`). Parts of the same aufs system may also be mounted elsewhere, functioning as a sort of grand symlink; Slax does this when you restore a session. Such links will mostly be resolved.
* One exception to the above: If you do an aufs-find on a parent of one of the aufs symlink-like sub-mounts, the contents of that sub-mount will not be seen. For example, in Slax, if you do `aufs-find /root` but `/root/Downloads` contains a mount of the aufs system with folder `/home/guest/Downloads`, the contents of that Downloads folder will not be seen; `aufs-list /root/Downloads` will show files that are not seen in `aufs-list /root`.
* Some tools are specific to files, and will ignore other objects like named pipes and sockets.

