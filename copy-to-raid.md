# Copying Files to the Windows RAID Machine

The Digital Archives Processing area has a Windows computer with a RAID (redundant array of independent disks) storage system. This system has 11 TB capacity and is used as temporary preservation storage for unprocessed collections material. Only a limited number of staff have access to this machine.

New digital accessions should be copied to the RAID (F: drive) after they have undergone [preliminary appraisal](./appraisal.md) and [virus scanning](./virus-scanning.md).

## Create a destination folder for the accession
1. Navigate to the appropriate library's folder on the F: drive. 
2. Create a new folder with the collection number (if one does not already exist).
3. Inside the (new or existing) collection folder, create a folder with the accession number.
4. If there are multiple digital accessions for this collection, create one more folder with the accession number inside the accession folder.
    * This folder will hold the actual collection materials and will be turned into a bag and renamed.
5. If there are multiple pieces of media in the accession, you will need to make an additional folders within the "bag" folder. Label each one with a DMID and any written information from the media's label.
    * Abbreviate the label information as needed to prevent the folder title from getting too long.

### Example folder structures
Collections with multiple digital accessions will need an additional folder level so that preservation documentation for each accession stays with the appropriate materials.

* __rbrl100__
   * __2022-01-er__
      * preservation_log.txt
      * bag_manifest-md5.txt
      * __2022-01-er_bag__
         * data
            * cd-001_Photos
               * pic001.jpg
               * pic002.jpg
            * cd-002_Speeches
               * speech.docx
   * __2022-02-er__
      * preservation_log.txt
      * bag_manifest-md5.txt
      * __2022-02-er_bag__
         * data
            * hd-001_Email2012
               * archive.ost
            * usb-001_Correspondence
               * letter_draft.docx
               * letter_final.pdf

* __rbrl101__
   * preservation_log.txt
   * bag_manifest-md5.txt
   * __2022-03-er_bag__
      * data
      *  f-001_PressReleases
         *  001.docx
         *  002.docx
         
## Copy the files to the destination folder.
6. [Connect the media to the RAID machine](./read-legacy-media.md) using the appropriate write protections and/or drive.
7. Copy the files to the appropriate folder using [TeraCopy](./teracopy.md).
8. Record the results of the copying process in the [preservation log](./preservation-documentation.md).

[Fixity information](./fixity.md) should be generated immediately after copying. 
