# Archive Script

## Description:

This is a simple script that makes use of the `p7zip-rar` package to create `.7z` type archive files or extract data from archive files.

## Features:
- Can archive and compress files and directories.
- Can extract files from archives.
- Autoinstalls dependencies (no preinstallations required).

## Installation:
- Simply copy paste the `archive` bash script in this repository or download it into your machine and run the following:

```bash
$ chmod +x ./archive
$ sudo mv ./archive /usr/local/bin # optional (you don't have to but it's easier to use the script from anywhere that way)
```

## Usage:
- Run: `archive ./path_to_file_or_directory` in your terminal.

- Examples:

```bash
$ archive ./some_archive.7z # example 1 --> produces ./some_archive/ directory with extracted files
$ archive ./some_archive.zip # example 2 --> produces ./some_archive/ directory with extracted files
$ archive ./some_archive.rar # example 3 --> produces ./some_archive/ directory with extracted files
$ archive ./some_file.txt # example 4 --> produces ./some_file.7z archive file
$ archive ./some_directory # example 5 --> produces ./some_directory.7z archive file
```

As you may have noticed, the command does two things:

1. It detects whether the file/directory in the given command argument is an archive file or just a normal file/directory, then it either archives or extracts based on that information.

2. The script can handle multiple archive extensions, e.g. `.7z`, `.rar`, and `.zip`. This benefit comes from the `p7zip-rar` package.

Therefore, you don't need to specify any additional info. Only the command followed by the path to your file or directory.

## Note

Any linux distribution that is based on Ubuntu and Debian (i.e. any distro that uses `apt` as its package manager) should be fine.
In linux distributions such as Arch for example (which uses `pacman`) some issues might occur. If you don't have `p7zip-rar` the script will actually try to autoinstall it for you. However, the command run to do that is `sudo apt install p7zip-rar`. This might not work in some linux distributions and you will have to install `p7zip-rar` on your own before using the script. Same for `sudo apt install file`.
A fix for this is possible (e.g. checking the OS release file) which I will work on adding soon.


