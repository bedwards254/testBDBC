---
layout: post
title:  Transferring data from floppy disks using Kryoflux, alternate version
category: jekyll 
description: Using the Kryoflux to transfer data from floppy disks and scripts! 
---

# Transferring data from floppy disks using the KryoFlux

### Before you begin:

* This workflow uses tools  in Windows. If necessary, restart the Digital Archives Lab workstation and boot to the Windows hard drive. You can find instructions on how to do this [here](https://bedwards254.github.io/testBDBC/jekyll/2019/01/22/BC-Windows-Switch.html).
* **Make sure the Digital Archives' Lab workstation is not connected to the internet.** Unplug the yellow ethernet cord at the back of the computer.
* As you unpack the KryoFlux, pay attention to the labels on the data cable and the KryoFlux enclosure. These will help ensure that the floppy disk drive and the KryoFlux are connected correctly.
* As you are setting up the KryoFlux, avoid placing any drives on the metal shelves over the workstations.

### Set-up instructions:

1. Using the data cable, connect the KryoFlux to the correct floppy disk drive.

   - The data cable has three connectors: one for the KryoFlux; one for 3.5" floppy disk drives; and one for 5.25" floppy disk drives. Each connector on the cable is clearly labelled.
    - The data cable's red wire signifies pin 1. When connecting the data cable to the KryoFlux, be sure to align the red wire with the **Pin 1** label on thestored KryoFlux enclosure.
  
2. Using the USB cable, connect the KryoFlux to the lab workstation.

**Check that the associated driver is correct:**

3. In the Windows Search Box, type `device manager` and hit **enter**.
4. From the list, select **Universal Serial Bus Controllers**. If you see **KryoFlux Disk System** listed here, you can skip to the next section.
5. If you do not see **KryoFlux Disk System** listed, select **Ports (COM & LPT)**.
6. Right-click on **Bossa Program Port**.
7. Select **Update driver software**.
8. Select **Browse my computer for driver software**.
9. Select **Let me pick from a list of device drivers on my computer**.
10. At this stage you should see **KryoFlux Disk System** listed. Select it and hit **Next**. You should see the following confirmation message: **Windows has sucessfully updated your driver software**. Hit **Close**.

### Complete KryoFlux set-up:
1. On the desktop, locate the folder titled **RunFiles**. 
2. Double-click to open, and locate the file **pre-run.bat**. 
3. Double-click on **pre-run.bat**, which will open the command prompt and automatically run the above command.

**NOTE:** The resulting prompt will likely say: **Control command rejected by the device. CM: maxtrack = 0**.

4. Ensure that the power cable is plugged in and connect the power adaptor to the back of the floppy disk drive.

    - The power adaptor has two connectors: the smaller one is for 3.5" floppy disk drives and the larger one is for 5.25" floppy disk drives. Both are clearly labelled.
    - When working with the 5.25" drive, in particular, be careful to make sure that the adaptor is properly aligned.
    - When disconnecting the adaptors, grip the white plastic piece and not the wires, as these are quite fragile and easily come loose if mishandled.
  
5. Insert a floppy disk.
6. On the desktop, locate the folder titled **RunFiles**. 
7. Double-click to open, and locate the file **pre-run.bat**. 
8. Double-click on **pre-run.bat**, which will open the command prompt and automatically run the above command. 

**NOTE:** The resulting prompt will likely say something like: **CM: maxtrack = 83**.

### Capture stream files:

1. Ensure that the Digital Archives hard drive dock is powered on.
* On the desktop, locate the folder titled **RunFiles**. 
* Double-click to open, and locate the file **run.bat**. 
* *COPY* the file into the *[collectionName]_diskImages* folder. 
* Navigate to the *[collectionName]_diskImages* folder in the command prompt.

**NOTE:** To navigate to the right drive, simply enter **[driveLetter]:** into the command prompt. 
* Example: ```L:```

From there, use the ```cd path\to\folder``` command to navigate to the directory. 
* Example: ```cd digitalArchives\diskImages\[collectionName]_diskImages``` 

2. In the command prompt type **run.bat [MSSnumber_ID]** and hit **enter**. 

3. Review the terminal output to determine which encoding format is correct:

    - Incorrect formats will register as ``unformatted``.
    - The correct format will be listed as ``OK``.
    - If MFM is the correct format, use ``-i4`` in step 21.
    - If Apple DOS 400/800 is the correct format, use ``-i9`` in step 21.
    - If neither format is correct, make a note of this and set disk aside for further review at a later date.
    
4. Once imaging is complete, remove the floppy disk from the drive.
5. Label the disk with its MSSnumber\_ID. Be sure not to obscure any original labels.

### Repeat for remaining floppy disks:

6. Insert next floppy disk.
7. Hit the *up arrow* while in the command prompt and edit the **run.bat [MSSnumber_ID]** command to the next disk number.

### Disconnect the KryoFlux:

1. Click the **Safely remove hardware** icon and select **KryoFlux Disk System**.
2. Once it is safe to remove the KryoFlux, carefully disconnect the power (taking care not to pull on the wires), then the USB cable, and finally the data cable.
3. Replace all components in the KryoFlux box and return to the cabinet.

[Next Step ->](https://bedwards254.github.io/testBDBC/jekyll/2019/01/22/img-migration.html)
[Home](https://bedwards254.github.io/testBDBC/jekyll/2019/01/23/welcome-BDBC.html)
