---
layout: post
title:  Optical discs
category: jekyll 
description: Instructions for imaging and Keep upload of optical discs
---

# Optical discs

### REVIEW OPTICAL DISC CONTENT:
1. Launch IsoBuster from the Desktop (Windows side).
2. Insert disc. After a few seconds, the disc’s file tree should load in the IsoBuster window.
3. Review the file tree to identify the contents of the disc:
- a. If the disc contains audiovisual data only, it should be re-routed through the AV workflow;
- b. If the disc contains non-audiovisual data only (e.g., documents, digital photographs), image using Guymager;
- c. If the disc contains mixed-mode data (both audiovisual and filesystem data), image using IsoBuster.

**NOTE:** For more information about the Rose Library’s approach to optical discs, see the 
[Capturing Data from Optical Discs policy](https://bedwards254.github.io/testBDBC/jekyll/2019/01/28/Optical-discs-policy.html).

**NOTE:** Check to see if the CD is a *CD-R* or a *CD-RW*. If the CD is a **CD-RW**, you will need to create a TAR file, using [these instructions](https://bedwards254.github.io/testBDBC/jekyll/2019/01/29/TAR-files.html). 

### CAPTURE DISK IMAGE USING GUYMAGER:
1. Switch to the BitCurator side of the machine. See [here](https://bedwards254.github.io/testBDBC/jekyll/2019/01/22/BC-Windows-Switch.html) for instructions. 
2. Right-click anywhere on the Desktop to create a new folder. Name it collectionName_diskImages_cds 
(e.g., Cleage_diskImages_cds).
3. Insert disc, if not already loaded.
4. Double-click the *Imaging Tools* folder on the Desktop.
5. Double-click *Guymager*.
6. Select the CD/DVD drive from the list.
7. Right-click and select *Acquire image*.
8. In the Acquire image window, complete the following:
- a. Select *Linux dd raw image*;
- b. De-select *Split image files*;
- c. Use the browse button (...) to the right of Image directory to navigate to the folder created at step 2;
    * i. NOTE: Go media/bcadmin/New Volume/ to reach the hard drive properly
- d. Enter an Image filename. Use *MSS#_ID* (e.g., 1000_01).
- e. Check every box underneath Hash calculation / verification (Calculate MD5, Calculate SHA-1, 
Calculate SHA-256, Re-read source after acquisition for verifications (takes twice as long), and Verify 
image after acquisition (takes twice as long))
9. Hit *Start*.

**NOTE:** You can check the progress of disk imaging by scrolling to the right in the Guymager window.

10. In the folder created at step 2, right-click the disk image file and select *Rename*.
11. Change the file extension from *.dd* to *.iso*.

**NOTE:** You can review the disk image contents by right-clicking the object and selecting Scripts > Mount Disk Image. 
The disk image will be mounted on the Desktop. Double-click to open it and view files.

**NOTE:** If you are doing multiple CDs at once, after you load the CD into the drive, hit “Rescan” in the top left corner of 
Guymager to have it appear in the list. 

### CAPTURE DISK IMAGE USING ISOBUSTER:
1. Switch to the Windows side of the machine. See [here](https://bedwards254.github.io/testBDBC/jekyll/2019/01/22/BC-Windows-Switch.html) for instructions. 
2. Power on the hard drive dock and create a new folder in the diskImages directory, named 
collectionName_diskImages (e.g., Cleage_diskImages).
3. Launch *IsoBuster*.
4. Insert disc, if not already loaded. After a few seconds, the disc’s file tree should load in the IsoBuster window.
5. Select the disc and right-click to open the *Extraction menu*.
6. Select *Extract CD <Image> > RAW (*.bin, *.iso)*.
7. Navigate to the directory created at step 2 and enter a file name for the disk image. Use MSS#_ID (e.g., 1000_01).
8. From the dropdown menu, change the *Save as* type to *.bin.
9. Hit *Save*.

**NOTE:** If IsoBuster encounters an unreadable sector, an error message will ask if you want to retry imaging, 
select one of four options and proceed with imaging, or quit. One selection will be checked by default 
(probably *Replace with User Data All Zeroes*). Leave the default selection checked and hit *Selection*. 
- *An Error(s) occurred during reading* window will ask if you want to delete the file.
- Click No. 
- Click *Save* on the next window that appears, saving it as a *.cue file. 

# Ingesting Optical Discs into the Keep

### Before you begin:
- The following steps can be performed from your own computer and do not require that you be in the Digital Archives Lab. 

**Ingest Bag into the Keep:**

1. Log into the Keep at https://keep.library.emory.edu.
2. Click *ingest uploaded content*.
3. In the Collection box, begin typing the collection name and select the correct one from the list that pops up.
4. From the File to ingest drop-down menu, select the first of your Bags.
5. Hit Submit.

**Complete Keep object metadata record:**

6. Click on the newly-ingested object’s PID in order to view its metadata record.
7. Complete **Descriptive Metadata**:
- The following fields should auto-populate:
- Collection
- Title
- Resource Type
- Genre
- Identifier

- Refer to the floppy disk label. If the label contains any notes regarding dates or content, 
enter them where relevant.
- Dates can be added to the *Covering Dates* field. Neither a date range nor full dates are required, so add as 
much or as little information as you have.
- Other label information can be added to the Abstractfield.

8. Complete **Technical Metadata**:
- The following fields should be completed:
  * **Imaging Date:** Enter the date on which you imaged the disk.
  * **Creating Application:** From the drop-down menu, select the application used to create the disk image. For all of our 
optical disks, this will be *Guymager (BitCurator 1.0) 0.7.3-1*.
  * **Original Environment Software:** Type *None* in all three Original Environment Software fields.
  * **Hardware Name:** Type *CD* or *DVD*.
  * **Hardware Type:** Select *removable media* from drop-down menu.
  * **Other information:** Type *Imaged using Guymager in BitCurator environment*.
9. Complete **Rights Metadata:** 
- The following field should be completed:
  * **Access Status:** Select *13: Metadata onlyfrom the drop-down menu*.
10. Hit *Save*.
