# Virus scanning

All donations received in digital form must be scanned for viruses. Content created by or digitized by a special collections department does not need to be scanned.

## 1. Quarantine files for a minimum of 30 days on transfer media (if necessary)

* Files should be at least a month old (from the date of their creation) before running the virus scan so that the antivirus program has time to update with the newest virus definitions. If files are received that have been in an active computing environment for less than 30 days, wait a minimum of 30 days before proceeding with accessioning.

* Files can be left on the original transfer media during the 30 day quarantine period. The rationale is that the transfer media we receive where the files are less than 30 days old are typically new external hard drives purchased for the transfer process that are unlikely to fail. If there is some unusual risk to the media in that time, files can be copied to a separate external hard drive.

* If a virus is detected that poses a potential threat to a donor's personal computing environment, reach out to the archivist or processor associated with the collection and let them know.

## 2. Connect the transfer media to an off-network computer

* The Digital Archives Processing Area includes a quarantine computer (disconnected from the network). It is running Windows 10 and has Wi-Fi access to keep the antivirus software updated. Prior to virus scanning, media should only be connected to this computer. Microsoft Defender Antivirus, the standard antivirus for Windows 10, can be used for the scanning process.

* [Connect the transfer media to the computer](./read-legacy-media.md), taking the necessary precautions to ensure that the media is read-only.

    * If it is a USB device, use a hardware write blocker (e.g. Wiebetech USB WriteBlocker )

    * If it is a 3.5" floppy disk, open the sliding tab so the computer cannot write to the disk.

    * The 5.25" floppy disk drive in the Digital Archives Processing Area is read-only.

    * CDs, DVDs, and other optical media (excluding CD/DVD-RW disc) can be assumed to be read-only.

## 3. Scan the media using Microsoft Defender Antivirus

* If this is the first time using this instance of Microsoft Defender, ensure that routine remediation is turned OFF. Otherwise the computer will attempt to clean or quarantine flagged files without prompting the user. Change this setting by editing the computer's group policy for Microsoft Defender Antivirus: the policy to "Turn off routine remediation" should be ENABLED.
    * The read-only protections listed above should prevent files from being altered by the antivirus software, but this feature should still be turned off as a precaution. 

* Open File Explorer and locate the drive or directory of files to be scanned. 

* Right-click on the drive or folder and select "Scan with Microsoft Defender..."

* This will automatically open the antivirus program and start a scan of the selected directory. 

* When scanning is complete, the Windows Security screen will display "No current threats" or "[#] threats found" and the specific files listed below. Record the results of the scan in the [preservation log](./preservation-log.md).

## 4. Remediate any viruses

* Put a label on the transfer media with the name of the possible virus.

* Determine the research value of the affected file. 
    * If the virus is attached to media that does not have enough research value to warrant remediation efforts, separate the media and do not copy it.
    * If the virus is a separate piece of malware, such as a spam email attachment, then the file can simply be exluded from copying.
    * If the virus is attached to a file of unknown research value, consult with the collection's archivist or processor to determine its importance.

* If the affected file is determined to have research value, research the virus name to confirm that it is an actual threat and not a false positive caused by an unusual file extension. 
    * If it is confirmed to be a false positive, make a copy of the file and change the extension to prevent issues with the antivirus software. Document the change in the preservation log.

* If the virus is confirmed or likely to be a real virus, copy the file to a piece of removable storage media and use Microsoft Defender to clean the copy of the affected file. Document this in the preservation log.
    * If the file cannot be cleaned and continues to trigger the antivirus software, additional avenues for data recovery will need to be explored. This may involve copying the content of the file through other means, or requesting a new copy of the file from the donor if possible. Document all actions in the preservation log and in the "Condition Description" field of the [ArchivesSpace accession record](./accession_record_archivesspace.md).

## 4. Document virus remediation actions

* Document all virus scanning results, remediation decisions, and remediation actions in the preservation log.

* Viruses should also be recorded in the "Condition Description" field of the ArchivesSpace accession record with a brief discription of the remediation measures.

* Separated media should also be recorded in the "Disposition" field in the ArchivesSpace accession record.

## 4. Address separated media

* If media has been separated from the accession because of a virus, document this in the "Disposition" field in the ArchivesSpace accession record.

    * If we have legal rights to the collection, dispose of the media in the manner indicated in the deed of gift. Typically it will be securely destroyed. Occasionally, a donor may request to have unwanted digital media returned to them.

    * If we do not have legal rights to the collection, retain the media until we do have the right to dispose of them. Store separately from media where we are retaining files and mark clearly as awaiting destruction after receiving a deed of gift.
