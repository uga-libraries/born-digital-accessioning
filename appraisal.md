# Appraisal of Born-Digital Archives

The Hargrett and Russell libraries use a collaborative appraisal process for born-digital materials. This includes initial media appraisal, an iterative technical appraisal phase, and finally a content appraisal phase. Our appraisal process leverages the expertise of both the digital archivist and collecting archivists to appraise digital files through the dual lens of preservation needs and research value. 

During the initial media appraisal, the digital archivist identifies any media that does not need to be copied. Once the remaining media is transferred, the digital archivist performs a technical appraisal. This includes assessing the materials’ storage demands, format usability, and potential processing needs. A full format report is generated, and files are immediately appraised out if they meet a list of technical criteria. The digital archivist makes note of any anticipated issues related to sensitive information or complex formats that could add significant processing time. 

During the content appraisal phase, the collecting archivist appraises the materials again based on their research value and relevance to the collection. This process is supplemented with the digital archivist's notes from their technical appraisal. Collecting archivists can make and document disposition information or provide instructions to the digital archivist. 

## Initial Media Appraisal

Use labels and information from the donor to identify media that does not need to be copied. This typically includes labeled software installation disks, other commercial products that are clearly outside the scope of the collection, or media that the donor has identified as a duplicate or accidental inclusion.

* This step occurs *after* all of the materials in the accession have arrived at the Libraries and *before* the [Digital Media Identifiers](./digital-media-identifier.md) (DMIDs) are assigned. 

* Do not assume that unlabeled media are blank unless they are sealed in their original packaging.

* This process can continue as the media are first connected to the quarantine computer for [virus scanning](./virus-scanning.md). If media are discovered to be blank, they can be appraised out prior to assigning a DMID.

* Files that are retained during media appraisal can still be appraised out later on. 

## Technical Appraisal and Format Analysis

Technical appraisal is performed as part of the accessioning process and is used to identify and immediately remove certain types of files. This saves space in our storage systems and doubles as a preliminary review of the accession’s complexity and potential processing needs. 

Information gathered during technical appraisal is helpful for:

*   Providing technical context for content appraisal
*   Determining the processing tier
*   Identifying issues that might require follow-up with the donor, e.g. missing or encrypted data 

Format analysis is an important part of this process. The format-analysis.py script uses FITS to identify the formats in an accession and automatically log any files that match our technical appraisal criteria, including temporay files, trashed files, and duplicates. It also identifies each file's format risk based on the Digital Preservation Framework created by the U.S. National Archives and Records Administration (NARA). See the script documentation in GitHub for more information.

### Content removed during technical appraisal

Technical appraisal decisions are made by the digital archivist and primarily deal with software- and system-generated files. Files removed during technical appraisal must fall into one of these specific categories:

* **Application data:** Includes cached data, configuration folders, and other unwanted data that is automatically stored by certain software

* **Encrypted data:** Data that is password-protected - if the donor cannot provide an unencrypted version, these files will be appraised out

* **Exact duplicates:** Must be confirmed by identical checksum information - when in doubt about de-duping, get a second opinion from the collecting archivist

* **Temp files:** Small, automatically-generated files designed to improve a program or operating system's performance

* **Trashed files:** Files that have been "thrown away" by the donor in a trash folder or recycling bin

* **Unwanted software:** Programs that are not dependencies for the collection material

### Information gathered during technical appraisal that affects the processing plan

*   Size and complexity of the file system (existing amount of organization and descriptive file naming)

*   Areas with potentially sensitive information

*   Areas that may require manual sampling

### Process

1. Run the technical-appraisal-logs.py script on the accession folder to generate an initial file manifest (see the script documentation in GitHub for detailed usage instructions)

2. If applicable, delete any obvious files that fall into the categories above - when in doubt, don't delete
    * If a file is a potential dependency (e.g. it may hold important metadata or contribute to another file's functionality), leave it as-is and remove it later if needed

2. Run the format-analysis.py script on the accession folder to generate a full format report (see the script documentation in GitHub for detailed usage instructions)

3. Investigate the files that the report has flagged for technical appraisal

4. Delete any relevant files that fall into the categories above - when in doubt, don't delete

5. If anything is removed, run technical-appraisal-logs.py again using the "compare" argument to generate a log of deleted files
    * This script can be run multiple times with the "compare" argument during technical appraisal - it is designed to update the existing deletion log

Technical appraisal is iterative, so steps 2-5 may be repeated multiple times during accessioning and appraisal. Update the deletion log whenever files are removed by running technical-appraisal-logs.py with the "compare" argument.

6. When technical appraisal is complete, use TeraCopy to create a copy of the accession in a folder called "Appraisal copy"
    * Only make copies once the collection is "complete," i.e. no more accessions are expected. If more materials need to be accessioned, continue with step 7 and make a copy once all accessions have undergone technical appraisal.

7. Run the technical-appraisal-logs.py script on the appraisal copy folder to generate a full file manifest

7. Write up a bulleted list of "Notes from Technical Appraisal" to pass on to the collecting archivist

    * These notes can be sent on via email or in a Trello card notification depending on the archivist's preference

    * Include a brief summary of substantive technical appraisal actions, e.g. "Omitted 10 software disks, de-duped backup of photo library based on checksum info"

    * Include any areas that may contain sensitive information, e.g. "Potential PII in folder C:/User/Desktop/taxes"

    * Include any areas that may require sampling, e.g. "3562 photos in folder Press/Photos/Opening Ceremony can potentially be sampled"

    * Include a summary of complex or problematic formats and their processing implications, e.g. "FD3-002 contains multiple high-risk SWF files. Will require reformatting if retained." or "Z-001 contains a single backup file with no format ID. Contents unknown. Will require further research if retained."

    * Be realistic when estimating processing labor - recommend that certain files are appraised out if it seems clear that they will require more work than they are worth in order to be useable

    * Ask questions if there are any appraisal decisions that could use a second opinion

8. Send "Notes from Technical Appraisal" to the collecting archivist and tell them where the appraisal copy is stored
    * The appraisal copy allows them to peruse and open files at will without risking unwanted changes to the only copy of the accession

9. If they send appraisal instructions back:
    * Perform the requested deletions on the original copy of the accession
    * Run the technical-appraisal-logs.py script with the "compare" argument to update the deletion log
    * Fill in the deletion log "notes" field with any provided rationale for the deletions

10. If they make their own deletions:
    * Run the technical-appraisal-logs.py script with the "compare" argument on the appraisal copy to create a deletion log.
    * If there were unintended file changes during appraisal, either restore the accidentally altered files or replicate the deletions on the original copy of the accession. 
    * If there is a low risk of unintended changes, make the appraisal copies the preservation copies and delete the old version.

# Documenting Appraisal Decisions

* Document all substantive appraisal decisions in the "Disposition Note" field in the [ArchivesSpace accession record](./accession_record_archivesspace.md). Include a brief description of why it was not kept.

   Examples:
   
   * 3 CDs of Adobe installation software.

   * 4 blank 3.5" floppy disks.

   * 1 thumb drive labeled "Posters" that donor says duplicate the paper materials.

   * 2 commercial DVDs of the movie "Kung Fu Panda" that are unrelated to the collection.

* The deletion log generated by technical-appraisal-logs.py will serve as a granular record of everything that has been removed. This log is stored in the collection folder alongside the other preservation documentation.
