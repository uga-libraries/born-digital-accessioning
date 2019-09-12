# Virus scanning

All donations received in digital form must be scanned for viruses. Content created by or digitized by a special collections department does not need to be scanned.

## 1. Quarantine files for a minimum of 30 days on transfer media (if necessary)

* Files should be at least a month old (from the date of their creation) before running the virus scan so that the antivirus program has time to update with the newest virus definitions. If files are received that have been in an active computing environment for less than 30 days, wait a minimum 30 days before proceeding with accessioning.

* Files can be left on the original transfer media during the 30 day quarantine period. The rationale is that the transfer media we receive where the files are less than 30 days old are typically new external hard drives purchased for the transfer process. They are therefore unlikely to fail and so it is not worth the staff time required to create a backup.

* Whenever practical, the donor should be asked to retain a copy of the files until after they receive confirmation from the archives that the files have copied safely to temporary preservation storage (e.g., SAN, Linux RAID, or LTO tape).

## 2. Connect the transfer media to an off-network computer

* Use the virus software installed on all campus computers (Trend Micro OfficeScan). Any computer with current virus software and without access to the UGA network can be used for virus scanning.

* The Digital Archives Processing Area includes a quarantine computer (disconnected from the network) that can be used for this purpose. The virus software can be updated on the quarantine computer using wireless internet access.

* There is also a machine in the processing area with an internal 5.25" floppy disk drive that can be disconnected from the network for virus scanning. The computer must use a VPN client to connect to the university network via wireless.

* Attach the transfer media to the computer, taking the necessary precautions to ensure that the media is read-only.

    * If it is a USB device, use a hardware write blocker (e.g. Wiebetech USB WriteBlocker )

    * If it is a 3.5" floppy disk, open the sliding tab so the computer cannot write to the disk.

    * If it is a 5.25" floppy disk, cover the notch in the disk with tape.

    * CDs, DVDs, and other optical media (excluding CD/DVD-RW disc) can be assumed to be read-only.

## 3. Scan the media using Trend Micro OfficeScan

* Open the program so that it displays a list of all the drives attached to the computer.

* Check the box next to the drive with the files to be scanned. Click the plus mark next to a drive to see details about its contents if needed.

* Click "scan" in the lower right to run the program.

    ![Running a scan in Trend Micro OfficeScan](./images/virus-scanning1.png)

* A pop-up window will open and show the progress of the scan.

    ![Scanning progress in Trend Micro OfficeScan](./images/virus-scanning2.png)

*  When scanning is complete, you will either see a box saying "Scanning is complete. No security risks were found" or a box describing security problems. Record the results of the scan in the [preservation documentation](./preservation-documentation.md).

## 4. Address any viruses

* Put a label on the transfer media with the name of the possible virus.

* If the media label indicates the materials are of high research value, research the virus name to see if it is an actual virus or likely a false-positive and determine a course of action. The two most common actions are:

    * Exclude this file when copying the files from the transfer media to temporary preservation storage if it is likely to be a virus, or you are unsure but it is unlikely to be an important archival document based on the file title. Use the quarantine computer to make the copy and scan the copied files for viruses before transferring them to a networked computer to be certain that no virus is introduced into the computing environment from the media during copying.

    * If the file is not likely a virus and is important, copy the file to temporary preservation storage and change the file extension after it is copied so it does not continue to trigger antivirus software.

* If it is unclear from the media label whether or not the materials are of high historic value, store the media to be re-evaluated during processing. Do not copy the files from the media. Make a note in the accession record about this media to ensure the processor is aware of them. In the [Archivists' Toolkit accession record](./accession-record_archivists-toolkit.md), this information should be recorded in the "Condition" field.

* If the media label indicates the materials are not of sufficient historic value to warrant the resources required to investigate a virus, separate the media.

    * If we have legal rights to the collection, dispose of the media in the manner indicated in the deed of gift. Typically it will be securely destroyed. Occasionally, a donor may request to have unwanted digital media returned to them.

    * If we do not have legal rights to the collection, retain the media until we do have the right to dispose of them. Store separately from media where we are retaining files and mark clearly as awaiting destruction after receiving a deed of gift.

    * Record a brief summary of what is not being kept in the [Archivists' Toolkit accession record](./accession-record_archivists-toolkit.md). This information should be recorded in the "Disposition Note" field.

* Record decisions relating to the media, including the results of any research, in the [preservation documentation](./preservation-documentation.md).
