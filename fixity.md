# Fixity

*Copied from the [2019 workflow](https://github.com/uga-libraries/born-digital-accessioning/tree/main/legacy-docs-2017-2019) with minor changes.*

All departments generate some kind of manifest of files in an accession, which at a minimum includes file paths and fixity information. It can also include file dates, size, and formats.

There are two methods currently in use: creating bags with an md5 manifest, or just an md5 manifest generated using the md5sum command line tool and saved as a text file.

## Bagging (preferred method)

Bag accessions using bagit.py, the command line version of the tool to generate fixity information and make it easy to check files later for completeness and authenticity by validating the bag. All the files for an accession should be put in a single bag named with the accession number.

For most accessions, make a bag using the [bagit-python library](https://github.com/LibraryOfCongress/bagit-python). The bag includes a file (manifest-md5.txt) with the MD5 and file path for every file. Fixity can be checked to see if any have changed by validating the bag. An accession should be bagged unless it is too large. If there is an error during bagging, make a MD5 manifest using the command line instead.


Bagit Instructions:


### 1. Make the bag

  `$ bagit.py --md5 /path/to/accession/folder`

Record this step in the [preservation documentation](./preservation-documentation.md).


### 2. Rename bag directory

Append "\_bag" to the end of the accession folder name (e.g., harg-ms-281_2017-01-er_bag).


### 3. Validate the bag

`$ bagit.py --validate /path/to/accession/folder_bag`

Record this step in the [preservation documentation](./preservation-documentation.md).


### 4. Save manifest

Save a copy of the bag manifest (manifest-md5.txt) with the preservation documentation so that an inventory of the accession is available without restoring the entire bag from tape.

Rename the file to add accession number to the front of the title (e.g., Harg_ms_2017_01_er_bag_manifest-md5.txt)
