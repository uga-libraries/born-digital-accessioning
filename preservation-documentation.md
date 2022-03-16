# Preservation Documentation

*Copied from the [2019 workflow](https://github.com/uga-libraries/born-digital-accessioning/tree/main/legacy-docs-2017-2019) with minor updates.*

Hargrett and Russell A&D uses a preservation log to record every action taken on a group of files, organized by accession and by each piece of removable media/file transfer. The log includes the action taken, tool used (if applicable), results of the action, and who performed the action.

There should be one preservation log per accession. The document is saved as a plain text, tab-delimited file (.txt) so we can later ingest all the documentation into a database that records preservation events for better use of the information.

This template was adopted prior to the University Libraries' implementation of [PREMIS metadata](https://www.loc.gov/standards/premis/). The information gathered was compared to PREMIS event metadata in 2017. The only information missing is an identifier and event type, both of which could be assigned once the metadata is ingested into a database. The "Action" field includes information that would be split into three PREMIS fields: detail information, outcome information, and agent (software). We will keep the current template for now so that all the metadata is structured consistently to facilitate ingest into a database, but may split this field at a later date.

## Information Recorded

Each row should only have information about one action taken on a single group of files (typically all files from a single piece of removable media or single transfer). Record preservation actions as you work through the accessioning process so that the documentation is accurate and up-to-date.

This documentation covers events from acquisition through appraisal. 

* **Collection number:** use lowercase letters, numbers, and dashes (e.g., rbrl-272-ti). This is included in the text rather than relying on the file title or the folder the file is saved in so that we have all necessary identifying information if the record is ever ingested into a database.

* **Accession number:** use lowercase letters, numbers, and dashes (e.g., 2010-62-er).  This is included in the text rather than relying on the file title or the folder the file is saved in so that we have all necessary identifying information if the record is ever ingested into a database.

* **Date:** format YYYY-MM-DD. For actions that span more than one day, record the date the process finished.

* **Media Identifier:** unique ID for the media the action was taken on ([Digital Media Identifier](./digital-media-identifier.md)).

* **Action:** include a description of the action, the software or hardware used to complete the action (if applicable), and the result. When applicable, use the standard language provided below to describe an action and its outcome.

* **Staff:** name of the staff person who performed the action.

    ### [View sample preservation log](./sample-preservation-log.txt)

## Examples of Standardized Language Used

### Virus Scanning

*   Virus scanned with Microsoft Defender Antivirus. No security threats were detected.

*   Virus scanned with Microsoft Defender Antivirus. The following files were identified as viruses: _[list file path and name]_.

*   This media contains a virus and does not have high research value. The media was not copied.

*   _[filename]_ was identified as containing a virus. After research, it was determined that this was a false positive. The file can be copied and the file extension will be changed to _[whatever used]_ so that the file will no longer be identified as a virus.

*   _[filename]_ was identified as containing a virus. After research, it was determined that this is likely a virus. Other files on this disk do have high research value. They were copied to removable media and re-scanned for viruses. _[filename]_ was excluded.

*   _[filename]_ was identified as containing a virus. After research, it was determined that this is likely a virus. The rest of the file has have high research value. It was copied to removable media, the copy cleaned with Microsoft Defender Antivirus, and re-scanned using the same software. No security threats were detected.


### Copying

*   Copied files from _[source]_ to _[location]_ using TeraCopy. No errors were detected.

    *   Common sources: transfer media, removable media

    *   Common storage locations: RAID, LTO tape _[number]_

    *   Common software: TeraCopy, rsync, Data Accessioner. Include the version number as well.

*   Attempted to copy files from _[source]_ to _[location]_ using TeraCopy.  _[describe errors]_

### Bagging

*   Bagged with accession _[accession number]_ using bagit.py. No errors were detected.

*   Validated bag for _[accession number]_ using bagit.py. The bag was valid.

### Appraisal (of previously copied files)

*   No files were kept from this disk after appraisal. The files were deleted from _[preservation location]_.
