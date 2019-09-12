# Create Accession Record in Archivists' Toolkit

*Used by Hargrett and Russell A&D.*

Provides a summary of each accession. Include description, size, dates, donation information, and technical information. Generate the accession record using information from the donor, the media labels, and bag manifest. Also save a copy of the bag manifest with the preservation documentation as a record of the files.

Even if digital records are received in an accession with other types of archival materials, create a separate accession record for the digital records to capture more detailed metadata and to make it easier for processing planning and preservation monitoring. The relationship between the rest of the accession and the digital records is maintained through the shared accession number and through notes in both accession records ("Arrival Status" and "Related Papers" in the accession record for the digital files and "Disposition Note" in the accession record for the papers).


## Archivists' Toolkit Accession Record

### Basic Information Tab

![Basic Information](./images/basic_info.jpg)

*   **Accession number:** Parsed into three fields, YYYY | ## | ER

*   **Accession date:** Formatted YYYY-MM-DD

*   **Resources Linked to this accession:**  Link to the resource record

*   **Collection type:**  Usually Papers, Records, or Collection, but could be more specific

*   **Collection title:** Official collection title

*   **Extent:**  Total file size of the accession folder in gigabytes, rounded to a quarter gigabyte.

    For smaller than a gigabyte:

    Gigabytes | Megabytes
    --------- | ---------
    0.001 | 0-1
    0.005 |	2-5
    0.01 | 6-10
    0.05 | 11-50
    0.1	| 51-100
    0.25 |	101-255
    0.5	| 256-512
    0.75 |	513-768
    1 |	769-1024

*  **Container summary:** Number of files in the accession folder (does include preservation documentation)

*  **Date expression:**  Inclusive date range

      *Mac/Linux* -- To generate a list of file dates (sorted newest first) in the terminal, change the directory to the folder with the accession files and use the `ls` command. Note: if only the month and day are displayed, that means the date is the current year.

      `$ find . -type f -print0 | xargs -0 ls -lt`

      To save the results to a text file for analysis, use above command with ">".

      `$ find . -type f -print0 | xargs -0 ls -lt > path/filename.txt`

      *Windows* --  The same can be accomplished in Windows wit the following command:

      `$ robocopy "/path/to/accession" "/path/to/accession" * /l /nocopy /is /s /njh /njs /nc /ns /ts | sort`

* **Date begin/end:**  First and last years of the inclusive date, formatted YYYY

*   **Bulk date begin/end (optional):**  First and last years of the bulk date, formatted YYYY

*   **General accession note (optional):**  Any additional information not covered elsewhere

### Accession Notes Tab

![Accession Notes](./images/accession_notes.jpg)

*   **Acquisition type:** Usually Gift

*   **Description:**  Scope and Content note, including any information from the donor

*   **Condition:** Note if unable to recover data from removable media, any visible damage to the media, or if there is a virus that needs to be addressed at the time of processing.

*   **Disposition Note:**  Note if any disks are not retained (e.g., duplicate CDs).

### User Defined Fields Tab

![User Defined Fields](./images/user_defined_fields.jpg)

*   **Date received:** Formatted YYYY-MM-DD

*   **Arrival status:**  How it was obtained by the library. Note the quantity and type of any removable media and their IDs, if applicable, and any information about how the files were copied from their original computing environment.

*   **Related papers:** If the media was found with related papers, indicate the box or folder it came from. Otherwise indicate "No related papers."

*   **Format:** List the main file formats, either by name or file extension.

*   **Donor Information:** Name and contact information of the donor.

### Names & Subjects Tab

![Names and Subjects](./images/names_subjects.jpg)

*   **Name link for creator:** Include link to Name Authority record for creator.

### Acknowledgements, Restrictions & Processing Tasks Tab

![Acknowledgements, Restrictions & Processing Tasks](./images/acknowledgements.jpg)

*   **Processing plan (optional):**  Note any advice for future processing (e.g., appraisal notes, etc.) and indicate if the materials were processed during accessioning. To aid in processing planning, Russell Arrangement and Description also notes the presence of unprocessed digital records in the Resource ID spreadsheet.

*   **Rights transferred note (optional):** Covered in the deed of gift.

*   **Access restrictions note (optional):**  Covered in the deed of gift (note if accession is closed for a specific duration of time).

*   **Use Restriction note (optional):**  Include if donor gave permission to put any files online.
