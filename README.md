Rename images based on their EXIF DateTimeOriginal field.
All images in the specified folder(s) are renamed following the format `YYYY.MM.DD_hh.mm.ss.v.ext` according to when it was taken.

### Usage

    img-rename [-h] [-r] [-d DIRECTORY]

    Rename image files based on the EXIF OriginalTime field.

    optional arguments:
      -h, --help            show this help message and exit
      -r, --recursive       enable recursive renaming in subdirectories
      -d DIRECTORY, --directory DIRECTORY
                            directory of files to rename (defaults to .)
