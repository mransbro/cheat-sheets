# Tar

## Compress a file or directory

```bash
tar -czvf /path/to/archive.tar.gz /path/to/directory-or-file
```

-c Create an archive.
-z Compress the archive with gzip.
-v Verbosely list files processed
-f Tells tar the next parameter is the archive file name

## Extract an archive

```bash
tar -xvzf /path/to/archive.tar.gz
```

-x  Extract files from an archive.
-v  verbosely list files processed
-z  Decompress the archive using gzip
-f  Tells tar the next parameter is the archive file name

## List an archive

```bash
tar -tvf /path/to/archive.tar.gz
```

-t  List the contents of an archive
-v  Verbosely list files processed
-f  Tells tar the next parameter is the archive file name