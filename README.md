# aufs-dir-tools

A set of small tools for managing files in the AUFS file system. Written in Bash with Porteus in mind, but may be useful on other AUFS distros (not tested).

License: [GPL v3](https://www.gnu.org/licenses/gpl-3.0.en.html). **There is no warranty; you run these programs at your own risk.**

* `aufs-find`: Find files by the number of versions they have.
* `aufs-list`: Find all the versions of one file in different overlaid branches.
* `aufs-clashes`: Find all file clashes between numbered branches.
* `aufs-diff`: Find the diff between any two versions (in different branches) of one file.
* `aufs-revert`: Delete the uppermost, writeable version of a file, without creating a whiteout.
* `aufs-unwh`: Remove whiteout deletion files for a path. 

## Install

To build a module on Porteus:

```bash
git clone https://github.com/lcpterid/aufs-dir-tools.git
cd aufs-dir-tools
./build-porteus
```

then activate or move it.

## Limitations

These tools work only if you have a single AUFS file system, and it is mounted at the root (`/`).
