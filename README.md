# Archive Script

## Description:

This is a simple script that makes use of the `p7zip-rar` and `tar` packages to create archive files or extract data from archive files.

## Features:
- Can archive and compress files and directories (specifically supports creating `7z`, `zip`, `tar`, and `.tar.gz` files).
- Can extract files from archives (supports extracting `rar`, `7z`, `zip`, `tar`, `.tar.gz`, and whatever else is supported by `p7zip-rar`).
- Autoinstalls dependencies (no preinstallations required)*.

***Note**: check [the note below](#note) if you're not running a linux distribution that uses the `apt` package manager (for e.g. a distro like Arch or anything not based on Ubuntu and Debian).

## Installation:
- Simply copy paste the `archive` bash script in this repository into an empty file or download the file into your machine and run the following:

```bash
$ chmod +x ./archive # mark file as executable
$ sudo mv ./archive /usr/local/bin # optional (you don't have to but it's easier to use the script from anywhere that way)
```

## Usage:
- Run: `archive ./path_to_file_or_directory` in your terminal.

- Examples:

```bash
$ archive ./some_archive.7z # example 1 --> produces ./some_archive/ directory with extracted files
$ archive ./some_archive.zip # example 2 --> produces ./some_archive/ directory with extracted files
$ archive ./some_archive.rar # example 3 --> produces ./some_archive/ directory with extracted files
$ archive ./some_file.txt # example 4 --> produces ./some_file.{type} archive file
$ archive ./some_directory # example 5 --> produces ./some_directory.{type} archive file
```

As you may have noticed, the command detects whether the file/directory in the given command line argument is an archive file or just a normal file/directory, then it either archives or extracts based on that information.

When archiving, you will be prompted with a menu:

![archive menu options](https://raw.githubusercontent.com/bosari-a/archive-script/main/assets/menu.png)

You can then enter the number representing the type of archive you want to create and press enter. The resulting archive will be at `./your_file_or_directory_name.{type_of_archive}`. E.g. `./some_name.tar.gz` if you entered `4`.

## Note

Any linux distribution that is based on Ubuntu and Debian (i.e. any distro that uses `apt` as its package manager) should be fine.
In linux distributions such as Arch for example (which uses `pacman`) some issues might occur. If you don't have `p7zip-rar` the script will actually try to autoinstall it for you. However, the command run to do that is `sudo apt install p7zip-rar`. This might not work in some linux distributions and you will have to install `p7zip-rar` on your own before using the script. Same for `sudo apt install file` and `sudo apt install tar`.
A fix for this is possible (e.g. checking the OS release file) which I will work on adding soon.


