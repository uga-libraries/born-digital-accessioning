# Accessioning Workflow for Born-Digital Archives
### The Hargrett Rare Book and Manuscript Library and The Richard B. Russell Jr. Library for Political Research and Studies, University of Georgia Special Collections Libraries

The following processes were instituted in November 2021. At that time, a new digital archivist role was established to manage born-digital, non-AV collections material for both the Hargrett and Russell libraries. This is a departure from the previous workflow, in which multiple archivists in separate libraries used similar processes to accession only their own library's digital materials. 

These born-digital accessioning processes are now the responsibility of the digital archivist and have been reworked and updated in collaboration with archivists from both libraries. This documentation builds on and updates the prior suite of [accessioning documentation](https://github.com/uga-libraries/born-digital-accessioning/tree/main/legacy-docs-2017-2019) from 2019 to reflect the Libraries' current workflow and technology.

## Overview

Accessioning is the process of transferring and documenting the transfer of collections material into the Libraries' care. For born-digital materials, that means safely copying them into the Libraries' temporary storage system and documentating the process. Digital files should be accessioned on receipt whenever possible. 

This documentation references Python scripts in the accessioning-scripts repository in the UGA Libraries GitHub.

## Purpose

The goals of this workflow:

1. Identify and appraise out any media that does not need to be copied.

2. Scan for and remediate any viruses.

3. Safely copy all digital files to temporary preservation storage.

4. Identify and appraise out any trashed or temporary files and unwanted software.

5. Verify the integrity of the copied files and generate baseline fixity information.

6. Generate an initial report of file formats.

7. Create appropriate backups of the copied files.

8. Document all decisions and actions performed on an accession.

9. Create an ArchivesSpace accession record.

10. Propose an initial processing plan.

## Procedure Overview

1. Receive the digital accession materials, the [accession number](./accession-number.md), and any separation notes from the archivist or processor working with the collection.

2. Perform an [initial media appraisal](./appraisal.md#initial-media-appraisal) to identify any media that does not need to be copied.

3. Start a [preservation log](./preservation-log.md) for the accession.

4. Begin [virus scanning](./virus-scanning.md) all media and transferred files. 

5. Assign retained media a [digital media identifier](./digital-media-identifier.md). Use the DMIDs to document the virus scan results in the log.

6. Start an [ArchivesSpace accession record](./accession_record_archivesspace.md). Document any preliminary appraisal decisions and any separation notes provided by the processor. 

7. Use [TeraCopy](./teracopy.md) to copy files from the media to the Digital Production Hub.

8. For media with extensive and useful label information, [transcribe label text](./media-labels.md) into a CSV.

9. Generate an [initial file manifest](./appraisal.md#process) of everything copied as part of the accession.

10. Generate a preliminary [format report](./appraisal.md#technical-appraisal-and-format-analysis) to assess initial risk and possible reformatting needs.

11. [Appraise out](./appraisal.md#technical-appraisal-and-format-analysis) any trashed or temporary files, unwanted software, and application data that is outside the collection's scope.

12. Bag the accession to generate verifiable [fixity information](./fixity.md).

13. Complete the accession record in ArchivesSpace.

14. Use TeraCopy to create a backup copy of the accession on LTO tape.

15. If no further accessions are expected for the collection, assign an initial processing tier for the collection. Otherwise, wait until all materials have been accessioned.

16. Create an [appraisal copy](./appraisal.md#process) of each accession and notify the collecting archivist that the collection is ready for content appraisal. Repeat technical and content appraisal as needed.

17. If additional materials are appraised out, update the bag along with all relevant logs and reports:
  * Deletion logs
  * Accession records
  * Format reports (only if the collection will need its formats monitored outside of the digital preservation system)

18. If necessary, update the assigned processing tier.

## Documentation Overview

The ArchivesSpace accession record provides a high-level overview of the accession materials, including their content and physical properties, and the accessioning process, including data recovery problems and major decisions related to appraisal and virus mitigation. This record is supplemented by additional preservation documentation saved in the accession folder.

### Script-generated documentation:

  * An initial manifest of all files copied as part of the accession, generated by technical-appraisal-logs.py

  * A deletion log of all files deleted from an accession, generated by technical-appraisal-logs.py

  * A copy of the bag manifest with fixity information for all files in the accession, generated by bagit.py

  * An aggregated format report generated by format-analysis.py

  * Accompanying format data generated by format-analysis.py (for closed collections in temporary storage, this is used for format monitoring and risk assessment while the materials wait to be ingested):
    * A folder of FITS XML files
    * A CSV of aggregated FITS format data
    * A CSV of NARA risk data

### Archivist-generated documentation:

  * A [preservation log](./preservation-log.md) with a date-stamped record of every action performed on the files
 
  * OPTIONAL: A list of [transcribed media labels](./media-labels.md), if applicable


## Policy Revision History

The first born-digital accessioning workflow was adapted from the Russell Library digital accessioning workflow. The first draft was completed in 2017 by Adriane Hanson (Head of Digital Stewardship), Callie Holmes (Digital Archivist, Brown Media Archives), and Steve Armour (University Archives Processing and Digital Archivist, Hargrett Library). It was revised again in 2019 by Steve Armour and Brandon Pieczko (Processing and Digital Archivist, Russell Library).

The initial version of this workflow was written in April 2022 by Emmeline Kaser (Digital Archivist, Digital Stewardship) and represents the processes in place from November 2021-May 2022. It was adapted from the 2019 revision of the prior workflow and reuses some sections wholesale, as noted.

The workflow was revised in October 2022 to include the collaborative appraisal and format analysis processes. Collaborative appraisal was introduced to the workflow in May 2022 and format analysis was introduced in June 2022.

The workflow was revised in January 2023 to reflect changes in the Libraries' temporary preservation storage options. 