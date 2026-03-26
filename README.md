# aufs-dir-tools

A set of small Bash tools for managing files in the `aufs` union file system. Written for use on portable Linux distros.

Tested on:

* Porteus 5.01 and 5.1
* Puppy Linux S15Pup64 22.12

License: [GPL v3](https://www.gnu.org/licenses/gpl-3.0.en.html). **There is no warranty; you run these programs at your own risk.**

These tools were written and tested by hand. No GPT coding agents were used to produce any of the code or documentation.

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

* These tools work only if you have a single AUFS file system, and it is mounted at the root (`/`). This currently prevents it from working well on Slax, which has two mounts of the same aufs file system.
* Some tools are specific to files, and will ignore other objects like naned pipes and sockets.

