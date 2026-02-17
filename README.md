# aufs-dir-tools

A set of small tools for managing files written in Bash

* `aufs-list`: Find all the versions of one file in different overlaid branches.
* `aufs-diff`: Find the diff between any two versions (in different branches) of one file.
* `aufs-find`: Find files by the number of versions they have.

To build a module on Porteus:

```bash
git clone https://github.com/lcpterid/aufs-dir-tools.git
cd aufs-dir-tools
./build-porteus
```

then activate or move it.
