# Fixity

A file manifest should be created for each born-digital accession at the point of accessioning. At a minimum, this manifest needs to include file paths and fixity information for every file in the accession. The current method for generating fixity information uses **bagit.py**. This creates a "bag" for each accession with an MD5 manifest text file inside. Bags are also easy to validate using bagit's command line program.

Below are instructions for creating and validating bags, as well as instructions for validating fixity information from checksum manifests created by other utilities. 

## Bagging

This workflow uses bagit.py, a Python module and command line utility with installation instructions on the Library of Congress's [bagit-python GitHub page](https://github.com/LibraryOfCongress/bagit-python). 

bagit.py turns a directory into a "bag" that includes a file (manifest-md5.txt) with the MD5 and path for every file. To validate a bag, bagit.py compares each file's current MD5 with the information in the manifest and will return "bag invalid" if there are any changes.

All the files for an accession should be put in a single bag named with the accession number.

Bagit Instructions:


### 1. Make the bag

  `$ bagit.py --md5 /path/to/accession/folder`

Record this step in the [preservation documentation](./preservation-documentation.md).


### 2. Rename the bag directory

Append "\_bag" to the end of the accession folder name (e.g., harg-ms-281_2017-01-er_bag).


### 3. Validate the bag

`$ bagit.py --validate /path/to/accession/folder_bag`

Record the results of this step in the [preservation documentation](./preservation-documentation.md).


### 4. Save the manifest

Save a copy of the bag manifest (manifest-md5.txt) outside the bag with the other preservation documentation.

## Verifying fixity from checksum manifests

### For bagged accessions:

 Fixity can be validated using a simple command line command.

 `$ bagit.py --validate /path/to/accession/folder_bag`


### For accessions with other kinds of checksum manifests:

Several older accessions have checksum manifests that were generated using the file cataloging utility Karen's Directory Printer. The UGA Libraries GitHub has a set of Python scripts that can parse and validate fixity from the MD5 checksums in these manifests. 
 * [verify-md5-KDPmanifests](https://github.com/uga-libraries/verify-md5-KDPmanifests) - UGA Libraries GitHub repo

