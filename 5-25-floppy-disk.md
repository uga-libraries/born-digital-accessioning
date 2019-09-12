# Imaging and Copying Files from 5.25" Floppy Disks

## Option 1: "Frankendrive" Gateway computer with 5.25” floppy drive

There is a computer in the Digital Archives Processing Area that is equipped with an internal 5.25" floppy drive ("Frankendrive") that is used for virus scanning and copying files from this type of disk. This drive will work with some, but not all legacy 5.25" floppy disk formats. If this machine does not recognize the formatting of the disk (error messages will indicate "incorrect disk architecture” or “disk needs to be formatted”), attempt to image the disk using option 2 below.

### 1. Scan Computer for Viruses

Since this machine is also used for virus scanning, run the virus scanner ([Step 3 of the virus scanning workflow](./virus-scanning.md) on the C:  drive of the computer to be absolutely sure that no viruses have been introduced to the hard drive before using the computer for preservation copying.

### 2. Connect the computer to the network

* Use the VPN (Cisco AnyConnect) to log into the address remote.uga.edu. Use your MyID name and password.

* Open the G: Drive. Click on "Groups on Lapis" icon on the desktop. User name is libs\username and the password is what you use to log in to your computer.

### 3. Copy the files

* Copy to the SAN with [TeraCopy](./teracopy.md).

* If writing to LTO tape, then copy from the SAN to the [LTO tape machine](./lto-tape-machine.md) (also using TeraCopy).

### 4. Disconnect the computer from the network

* Disconnect from the G: Drive by right clicking on the drive icon on the desktop and clicking "disconnect".

* Disconnect from the VPN by right clicking on the icon on the task bar (lower right, near the clock). The Cisco logo is a white circle with two lines arching through it.

* Turn off the computer.


## Option 2: FC5025 USB 5.25" floppy controller

The [Device Side Data FC5025 USB 5.25" floppy controller](http://www.deviceside.com/fc5025.html ) plugs into a USB port and enables you to attach a 5.25" floppy drive.

    The FC5025 can read the following disk formats:

        * Apple DOS 3.2 (13-sector)

        * Apple DOS 3.3 (16-sector)

        * Apple ProDOS

        * Atari 810

        * Calcomp Vistagraphics 4500

        * Commodore 1541

        * Kaypro 2 CP/M 2.2

        * Kaypro 4 CP/M 2.2

        * MS-DOS

        * Motorola VersaDOS

        * North Star MDS-A-D

        * PMC MicroMate

        * Tandy Color Computer Disk BASIC

        * TI-99/4A

In order for the floppy controller to work properly, the necessary drivers must be installed on the machine to which it will be attached. These drivers are available [online](http://www.deviceside.com/drivers.html), on the desktop of the virus quarantine computer, and on CD stored with the controller box. The necessary drivers and software have already been installed on the virus quarantine machine.

More detailed installation and operation instructions for the FC5025 floppy controller are available in the [installation and operation manual](./linked-documents/fc5025-installation-operation.pdf).

### 1. Attach the FC5025 floppy controller to virus quarantine machine

Attach the box containing the FC5025 floppy controller to the virus quarantine computer using the USB cable and plug in the power source.

### 2. Insert 5.25" disk into the floppy drive and close latch

### 3. Run the virus scanner ([Step 3 of the virus scanning workflow](.virus-scanning.md) on the floppy disk to ensure that it does not contain virus.

### 4. Create image of the disk and/or copy files from the disk

* Using the graphical Disk Image and Browse tool
    
    * To start the Disk Image and Browse tool under Windows, open the USB Floppy program group in the Start Menu or on the Desktop and click on Disk Image and Browse.

    * Select the type of disk you want to read from drop down menu (additional research may be required in order to identify the formatting of the disk).

    * Either click Browse to copy individual files from the disk (for some formats only), or enter a directory and filename and click Image to make an image copy of the entire disk.

* Using the command line tools
  The following commands can also be sent to the program using the command line interface:
  
  * fcbrowse - Browse and copy files from floppy disk
  
  * fcdrives - List connect FC5025 controllers
  
  * fcformats - List supported floppy disk formats
  
  * fcimage  - Capture disk image of floppy disk

More detailed instructions for interacting with the FC5025 floppy controller via the command line are available in the [documentation](./linked-documents/fc5025-commands.pdf).
