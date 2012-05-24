Script for renaming images based on their EXIF DateTimeOriginal field.
All images in the specified folder(s) are renamed following the format `YYYY.MM.DD-hh.mm.ss.v.ext`, based on when it was taken.

Images without the field set, or without EXIF data altogether, are ignored.
Should multiple images have the same DateTimeOriginal values, the script will prompt for a postfix to append to the filename.

### Usage

    img-rename [-h] [-r] [-d DIRECTORY]

    Rename image files based on the EXIF OriginalTime field.

    optional arguments:
      -h, --help            show this help message and exit
      -r, --recursive       enable recursive renaming in subdirectories
      -d DIRECTORY, --directory DIRECTORY
                            directory of files to rename (defaults to .)
