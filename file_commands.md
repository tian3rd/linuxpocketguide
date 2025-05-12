# File commands

## 7z

```bash
# install
sudo apt install p7zip-full

# extract from parts, it will find all parts and extract them
7z x archive.7z.001
```

## shasum

```bash
# compare two files to check if they are the same
shasum -a 256 file1 file2
```

## find

```bash
# find a file
find /path/to/search -name "filename" -type f
# print all dirs
find /path/to/search -type d -print
# find all files with a specific extension
find /path/to/search -name "*.txt" -type f
# find all files modified in the last 24 hours
find /path/to/search -type f -mtime -1
# only find immediate children
find /path/to/search -maxdepth 1 -mindepth 1
```
