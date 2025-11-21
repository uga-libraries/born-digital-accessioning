# Fixity

A file manifest should be created for each born-digital accession at the point of accessioning. After an accession is copied into the Libraries' storage systems, use [technical-appraisal-logs.py](https://github.com/uga-libraries/accessioning-scripts/blob/main/technical-appraisal-logs.py) to generate an initial file manifest of all the files and their checksum information. 

The current workflow also generates fixity information using **bagit.py**. This creates a "bag" for each accession with an MD5 manifest text file inside that is quick and easy to validate using bagit's command line program.

Below are instructions for creating and validating bags, as well as instructions for validating fixity information from checksum manifests created by other utilities. 

## Small Accessions (One Bag)

Smaller accessions should be put in a single bag named with the accession number.
We're still working on the threshold, but it is around 100-200GB and 10,000 files.

This workflow uses bagit.py, a Python module and command line utility with installation instructions on the Library of Congress's [bagit-python GitHub page](https://github.com/LibraryOfCongress/bagit-python). 

bagit.py turns a directory into a "bag" that includes a file (manifest-md5.txt) with the MD5 and path for every file. To validate a bag, bagit.py compares each file's current MD5 with the information in the manifest and will return "bag invalid" if there are any changes.

Bagit Instructions:


### 1. Make the bag

  `$ bagit.py --md5 /path/to/accession/folder`

Record this step in the [preservation log](./preservation-logn.md).


### 2. Rename the bag directory

Append "\_bag" to the end of the accession folder name (e.g., harg-ms-281_2017-01-er_bag).


### 3. Validate the bag

`$ bagit.py --validate /path/to/accession/folder_bag`

Record the results of this step in the preservation log.

### 4. Save the manifest

Save a copy of the bag manifest (manifest-md5.txt) outside the bag with the other preservation documentation.

## Verifying fixity from checksum manifests

### For bagged accessions:

 Fixity can be validated using a simple command line command.

 `$ bagit.py --validate /path/to/accession/folder_bag`


### For accessions with other kinds of checksum manifests:

Several older accessions have checksum manifests that were generated using the file cataloging utility Karen's Directory Printer. The UGA Libraries GitHub has a set of Python scripts that can parse and validate fixity from the MD5 checksums in these manifests. 
 * [verify-md5-KDPmanifests](https://github.com/uga-libraries/verify-md5-KDPmanifests) - UGA Libraries GitHub repo

## Large Accessions (Multiple Bags)
When bags are over a certain size, they become inefficient for ongoing fixity validations. 
We're still working on the threshold, but it is around 100-200GB and 10,000 files. 
Because of this, large accessions need to be split into multiple bags, while maintaining the original file directory structure.

### 1. Prepare directory
Add "_bags" to the end of any folder name, including the accession folder and media folder, that will contain multiple bags.
This will let scripts correctly identify accessions which are split into multiple bags.

If the accession came on multiple pieces of media and each is small enough, these will each be bagged.
Bag each one separately for consistency, even if some bags will be very small.

If any pieces of media are too large, the subfolders within them will each be bagged.
Any files that are not in a subfolder should be moved to a folder that repeats the name of the media folder.
Any of these subfolders could be split into bags if they are huge, but generally we stop at the subfolder.

Example:
2025-01-er_bags
   - cd001 [will be bagged]
   - cd002 [will be bagged]
   - hd001_bags
      - folder1 [will be bagged]
      - folder2 [will be bagged]
      - hd001 [will be bagged, contains loose files within hd001]
      - more_folders [will be bagged]
    
### 2. Make and validate bags
Use the [batch_bag.py script](https://github.com/uga-libraries/bags) to make bags of every folder within a parent folder.
It will make and validate each bag, and produce a log named bag_validation_log.csv.
It will skip any folder that ends in "_bags", since they need to be further split.

In the example directory in the previous step, the script would be run on 2021-01-er_bags and then run on hd001_bags.

If the script breaks or is otherwise interrupted, it can be restarted.
First, review the log and address errors from renaming the folder to add "_bag", so the script does not put this bag in another bag.
Then, run the script with the same argument (parent folder) as before. 
It will skip anything that ends in "_bag" or "_bags".

### 3. Address Errors

There may be a PermissionError when bagit tried to rename its temporary folder to "data".
We have not diagnosed why this is happening. To fix it:
- Use bagit.py or batch_bag.py (depending on how many there are) to bag them again, with the temporary folder in place
- Move the files out of the temporary folder
- Delete the temporary folder
- Update the paths in manifest-md5.txt to remove the temporary folder
- Update the MD5 for manigest-md5.txt in tagmanifest-md5.txt
- Validate the bag with bagit.py

There may be a PermissionError when the script tried to rename the folder to add "_bag".
We have not diagnosed why this is happening. To fix it:
- Rename the folder to add "_bag"
- Validate the bag with bagit.py

If the PermissionError persists, a bag can also be made "manually":
- Move the content into a folder named "data"
- Copy the four bag metadata files from another bag
- For bag-info.txt, update the Bagging-Date and Payload-Oxum (bytes.file_count)
- For bagit.txt, no change is needed
- For manifest-md5.txt, use md5deep or another tool to calculate the fixity for each file in the data folder
- For tagmanifest-md5.txt, update the MD5 for bag-info.txt and manifest-md5.txt
- Validate the bag with bagit.py

### 4. Update the preservation_log.txt

Summarize the rationale and steps taken to make bags of each media folder and/or subfolder in the preservation_log.txt for the accession.
Include more detail about any PermissionError and how it was resolved.
Once this is done, the bag_validation_log.csv may be deleted.

Example summary:

Splitting the bag for accession 2025.01.ER into multiple bags, because it is too big for sustainable management. There are three top folders. 
cd001 and cd002 will each be a bag and hd001 will be split into one bag per subfolder. Bags were created with batch_bag.py. The bags are valid.

Example texts for resolving errors (also include the initial error message as a separate item in the log):

Bagged with batch_bag.py a second time, still with the temp folder that could not be renamed to data. Moved out of the temp folder, deleted it, and updated the bag metadata files. Validated the bag with bagit.py. The bag is valid.

Renamed folder to add "_bag". Validated with bagit.py. The bag is valid.

Moved content into a folder named "data" and added the bag metadata files. The MD5s were created with md5deep64. Validated the bag with bagit.py. The bag is valid.
