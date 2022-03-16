# Accessioning Workflow for Born-Digital Archives
### The Hargrett Rare Book and Manuscript Library and The Richard B. Russell Jr. Library for Political Research and Studies, University of Georgia Special Collections Libraries

The following processes were instituted in November 2021. At that time, a new digital archivist role was established to manage born-digital, non-AV collections material for both the Hargrett and Russell libraries. This is a departure from the previous workflow, in which multiple archivists in separate libraries used similar processes to accession only their own library's digital materials. 

These born-digital accessioning processes are now the responsibility of the digital archivist and have been reworked and updated in collaboration with archivists from both libraries. This documentation builds on and updates the prior suite of [accessioning documentation](https://github.com/uga-libraries/born-digital-accessioning/tree/main/legacy-docs-2017-2019) from 2019 to reflect the Libraries' current workflow and technology.

## Overview

Accessioning is the process of transferring and documenting the transfer of collections material into the Libraries' care. For born-digital materials, that means safely copying them into the Libraries' temporary storage system and documentating the process. Digital files should be accessioned on receipt whenever possible. 

## Purpose

The goals of this workflow include:

1. Identify and appraise out any media that does not need to be copied.

2. Scan for and remediate any viruses.

3. Safely copy all digital files to temporary preservation storage.

4. Verify the integrity of the copied files and generate baseline fixity information.

5. Create appropriate backups of the copied files.

6. Document all decisions and actions performed on that accession.

7. Create an ArchivesSpace accession record.

## Procedure Overview

1. Receive the digital accession materials, the [accession number](./accession-number.md), and any separation notes from the archivist or processor working with the collection.

2. Perform a [preliminary appraisal](./appraisal.md) of the entire accession.

4. Start a [preservation log](./preservation-documentation.md) for the accession.

3. Begin [virus scanning](./virus-scanning.md) all media and transferred files. Continue to [appraise out](./appraisal.md) any blank or unreadable media discovered during this process. 

4. Assign retained media a [digital media identifier](./digital-media-identifier.md). Use the DMIDs to document the virus scan results in the [log](./preservation-documentation.md).

5. Start an [ArchivesSpace accession record](./accession_record_archivesspace.md). Document any preliminary appraisal decisions and any separation notes provided by the processor. 

6. Use [TeraCopy](./teracopy.md) to copy files from the media to the [Windows RAID machine](./copy-to-raid.md).

10. Generate baseline [fixity information](./fixity.md) for the copied files.

12. Complete the accession record in ArchivesSpace.

11. Use TeraCopy to create a backup copy of the accession on LTO tape.

## Documentation Overview

The ArchivesSpace accession record provides a high-level overview of the accession materials, including their content and physical properties, and the accessioning process, including data recovery problems and major decisions related to appraisal and virus mitigation. This record is supplemented by additional preservation documentation saved in the accession folder, including:
  * A detailed preservation log with a date-stamped record of every action performed on the files
  * A copy of the bag manifest with fixity information for every file in the accession


* **Preservation Documentation** – documentation of any action taken on the files

  [Instructions](/preservation-documentation.md)      


* **Fixity** – may also include other metadata extracted from the files

  [Instructions](./fixity.md)

* **Accession Record** - summary record about the accession

  [Instructions](./accession_record_archivesspace.md)

## Policy Revision History

The first born-digital accessioning workflow was adapted from the Russell Library digital accessioning workflow. The first draft was completed in 2017 by Adriane Hanson (Head of Digital Stewardship), Callie Holmes (Digital Archivist, Brown Media Archives), and Steve Armour (University Archives Processing and Digital Archivist, Hargrett Library). It was revised again in 2019 by Steve Armour and Brandon Pieczko (Processing and Digital Archivist, Russell Library).

The current workflow was written in 2022 by Emmeline Kaser (Digital Archivist, Digital Stewardship). It is adapted from the 2019 revision of the prior workflow and reuses some sections wholesale, as noted.
