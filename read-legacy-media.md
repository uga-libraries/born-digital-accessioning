# Reading and Copying from Legacy Media 

The Digital Archives Processing Area has several USB drives that allow us to connect legacy media to workstation computers. Remember that media *should not* be connected to a networked computer until it has been [scanned for viruses](./virus-scanning.md).

## Optical discs (CDs/DVDs)
* Use a USB optical drive to read CDs and DVDs on any computer with a vertical disk tray. Disks can slip out of this tray and get stuck inside the tower, so a USB drive is a safer option.

## USB storage media (flash drives/hard drives)
* Use a hardware write blocker (Weibetech USB write blocker) when connecting a USB storage device to a computer. 

## 3.5" floppy disks

* Ensure the sliding tab is open so the computer cannot write to the disk.

* Connect the USB floppy disk drive to the workstation. If the drive does not show up in File Explorer, try the following:
    * Open the Windows Settings pane
    * Select "Devices" > "Related settings" > "Devices and Printers"
    * Right-click on the USB floppy drive > "Browse files..."
    * When the File Explorer window opens, right-click on the floppy drive on the left side of the window > "Pin to Quick Access"

    This will pin the drive in File Explorer so it will be there the next time the drive is connected.

* Floppy disks can be virus-scanned while they're in the drive.

* This media can be slow to copy. For large collections of 3.5" floppy disks, it may save time to copy the files to a piece of removable media immediately after virus scanning. That way, there is only a single copying process from the storage media to the [RAID machine](./copy-to-raid.md) and no need to re-read each individual disk.

## 5.25" floppy disks

* The Digital Archives Processing Area has a 5.25" floppy disk drive with a [Device Side Data FC5025](http://www.deviceside.com/fc5025.html) USB 5.25" floppy controller. It requires specific drivers to work, which are currently installed on the off-network quarantine computer. They are available [online](http://www.deviceside.com/drivers.html) and on a CD stored in the Digital Archives Processing Area.

* There is no way to run the virus scanning software on this drive because the floppy controller is not recognized by the computer the way a regular USB drive would be. Files must be copied directly from the floppy disk to a piece of removable storage media using the FC5025 companion software, WinDIB. They should be scanned for viruses once they have been copied.

### Instructions for using the FC5025 floppy controller

1. Connect the drive to the quarantine computer using the USB connection, then plug in the power source. 

2. Open WinDIB, the FC5025 companion software. You can find it by searching for "Disk Image and Browse" on Windows. 

3. If the controller is on and working, you will see "FC2025 Floppy Controller" in the Source Drive field. 
    * If not, completely unplug the drive and plug it back in after a few minutes.

4. Insert a disk into the drive and flip the latch down.

5. Select a Disk Type from the dropdown menu. The most common types are **MS-DOS 1200k** and **MS-DOS 360k**, but the FC5025 can read all of the following formats:

    * Apple DOS 3.3 (16-sector)
    * Apple DOS 3.2 (13-sector)
    * Apple ProDOS
    * Commodore 1541
    * TI-99/4A 90k
    * TI-99/4A 180k
    * TI-99/4A 360k
    * Atari 810
    * MS-DOS 1200k
    * MS-DOS 360k
    * North Star MDS-A-D 175k
    * North Star MDS-A-D 350k
    * Kaypro 2 CP/M 2.2
    * Kaypro 4 CP/M 2.2
    * CalComp Vistagraphics 4500
    * PMC MicroMate
    * Tandy Color Computer Disk BASIC
    * Motorola VersaDOS

6. Click "Browse Contents." If the selected disk type is correct, then the window will display a list of files or "No files to display" (indicating a blank disk). 
    * If the disk type is incorrect, it will display "Unable to get file listing" or "Unable to begin reading disk." Continue to test different disk types until the correct one is found or all options are exhausted.

7. Once the correct disk type has been found, set the "Output Image Directory" to whatever destination folder you want to save the files (copy directly to a piece of removable media).

8. Change the "Output Image Filename" to the [Digital Media Identifer (DMID)](./digital-media-identifier.md).

9. Click "Capture Disk Image File" and wait for the process to complete.
    * Disk imaging with WinDIB has proven to be a faster and more effective transfer method than copying individual files.

10. Document the results of the copying process in the [preservation log](./preservation-documentation.md), including any read errors.

11. Disk images created by WinDIB often cannot be mounted (no known reason why). But the files can be extracted with no issue using 7-Zip.
    * Right click on the disk image > 7-Zip > "Extract here"

12. Make sure to [scan the extracted files for viruses](./virus-scanning.md). 

13. Eject the 5.25" floppy disk by flipping the latch up and removing it from the drive.
