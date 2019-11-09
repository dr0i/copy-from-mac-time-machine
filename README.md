About
=====

"Copy data from a Time Machine volume mounted on a Linux box".

This is a copy of @vjt's gist at https://gist.github.com/vjt/5183305, just as a repo, to allow opening issues, Pull Requests etc.

It copies files from an Apple Mac Time Machine backup to a "normally structured" (i.e. with reconstructed directory trees) file system.

Installation
============
(tested on a Debian based Gnu/Linux 4.4.)

Prerequisites: access to a terminal.

Mount the hdfs volume where your Mac's Time Machine backup was created.

Get the script by cloning this repo, or, even simpler, copying the [script](https://raw.githubusercontent.com/dr0i/copy-from-mac-time-machine/master/copy-from-time-machine.sh) into a newly created file named `copy-from-time-machine.sh`.

It's important to set the executable permission on the file, because it recursively calls itself:

```bash
chmod +x copy-from-time-machine.sh
```
Run the script - doing this as `sudo` avoids possible file permission problems:

```bash
sudo ./copy-from-time-machine.sh $source $target
```

where `$source` is the mounted Time Machine Volume and the proper directory (e.g. could be "Latest") and `$target` is the directory where you want to have the files copied to.

As a third argument the path of `.HFS+ Private Directory Data\r` could be given, if it wasn't detected by the script.
