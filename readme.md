# picsort

Yet another tool to sort media based on metadata. This one has very few dependencies and was writtin in bash.

**Key Features:**

- Tries to use EXIF data and filename to sort by date ($destdir/YYYY/YYYY-MM-DD/$file)
- No database needed
- Safely merge directories with duplicate data
- Filter based on mime type, size and file extension
- Very slow, but it actually works
- Dry run option to show you what will happen without actually making any changes

## Usage

```
$ ./picsort -h


picsort: [options] source [destination directory]

options:
  --delete                                      delete source files after copying (disabled by default)
  -d, --dry-run                                 don't actually copy or move any files, just output what would have happened without this option
  -E, --exclude ""                              case-insensitive, space-separated list of extensions to skip (by default filename is irrelevant)
  -e, --extensions ""                           case-insensitive, space-separated list of extensions to process (by default filename is irrelevant)
  -h, --help                                    print this message and exit
  -n, --disable-mimetype                        disable mimetype checking (NOTICE: this relies only on -e and -E and by default will process ANY file)
  -m, --min-size 200K                           minimum filesize to process (refer to find command '-size' argument for syntax)
  -M, --max-size 50M                            maximum filesize to process (refer to find command '-size' argument for syntax)
  -t, --mimetype-pattern "(image|video)/.*"     mime type pattern to process (refer to 'grep -E' syntax)
  -s, --silent                                  output nothing, not even errors
  -v, --verbose                                 verbose output

  source                                        source directory containing media to process
  destination                                   the destination directory (optional if PS_DESTDIR env var is set)
```

## References

- metadata: https://web.archive.org/web/20180919181934if_/http://www.metadataworkinggroup.org/pdf/mwg_guidance.pdf
- meetadata date/time: https://web.archive.org/web/20180919181934if_/http://www.metadataworkinggroup.org/pdf/mwg_guidance.pdf#page=37
