---
layout: post
title:  Migrating KryoFlux image files in preparation for ingest
category: jekyll 
description: Migrating from img files to E01 files
---

# Migrating KryoFlux image files in preparation for ingest

### Before you begin:

* This workflow uses tools stored as part of the BitCurator suite. If necessary, restart the Digital Archives Lab workstation and boot to the BitCurator hard drive. You can find instructions on how to do this [here](https://bedwards254.github.io/testBDBC/jekyll/2019/01/22/BC-Windows-Switch.html).
* Ensure that the Digital Archives Lab workstation is not connected to the Internet by unplugging the ethernet cable.

### Locate existing image files:

1. Ensure that the Digital Archives hard drive dock is powered on. 
2. Ensure that the Digital Archives hard drive is mounted inside BitCurator. If necessary, double-click the **New Volume** icon in the toolbar on the left-hand side of the screen. Once the Digital Archives hard drive is mounted, a **New Volume** icon will appear on the Desktop.
3. Double-click the **New Volume** icon on the Desktop and navigate to the **[collection]_diskImages** folder.
4. Open a terminal window but right-clicking anywhere on the Desktop and selecting **Open Terminal**.

### Run the script:

1. Locate *migration.bash* on the desktop and double-click. 
2. The file should look like this: 

:: 

	cd /media/bcadmin/New\ Volume1/digitalArchives/diskImages/[collectionName]_diskImages/

	for i in [MSSNumber]_{ID..ID}
		do
		
		md5sum $i/$i.img >$i/imgMD5.txt
		
		ewfacquire ./$i/$i.img -C "$i" -D "3.5 inch floppy disk" -e “[netID]” 
		-E “[collection title]” -f "encase6" -m "removable" -M "logical" -N "Migration from img" 
		-c "deflate" -o 0 -S "1.4 GiB" -P 512 -g 64 -t ./$i/$i
		
		ewfverify $i/$i.E01 >$i/verify$i.txt
		
		done

3. Edit the information in brackets [ ] above to match your collection information. The ID numbers should equal
the folder numbers you are wanting to migrate. 

*For example*: 

::

	cd /media/bcadmin/New\ Volume1/digitalArchives/diskImages/Mackey_diskImages/
	
	for i in 123_{01..06}
		do 
		
		md5sum $i/$i.img >$i/imgMD5.txt
		
		ewfacquire ./$i/$i.img -C "$i" -D "3.5 inch floppy disk" -e "bedwa24" 
		-E "Nathaniel Mackey papers" -f "encase6" -m "removable" -M "logical" 
		-N "Migration from img" -c "deflate" -o 0 -S "1.4 GiB" -P 512 -g 64 -t ./$i/$i
		
		ewfverify $i/$i.E01 >$i/verify$i.txt
		
		done

*This will run the MD5 checksum, the migration to E01 format, and verify the checksum for img folders/files 01 through 06 in one command.* 

4. **SAVE** the file and close it. 

	*If you do not save the file, the script will not run correctly*

5. In the terminal, navigate to the Desktop using

    ```cd Desktop```

6. Type **bash migration.bash**
7. Hold down **enter** until you are back to the original prompt ($). 

<!-- ## Review MD5 checksum and verify checksum files -->

<!-- Using the **MD5.bash** file, the MD5 file and verify files created during the migration process can be compared against one another to make sure they are the same values.  -->

<!-- **NOTE:** The *.bash* file and the Python file of the same name must be in the same directory. One does not work without the other. -->

<!-- 1. Open the **MD5.bash** file. 
2. Edit the file path to direct to the collection folder, similar to how you did above. 
	* If you type an invalid file path and run the file, an error message will appear.
3. **SAVE** the file. 
4. Open a terminal window but right-clicking anywhere on the Desktop and selecting **Open Terminal**.
5. In the terminal, navigate to the Desktop using

    ```cd Desktop``` -->

<!-- 6. Type **bash MD5.bash** and hit **enter**
7. The results of the scan will appear in the terminal window, either "Success!" or "Fail!" next to the folder number. -->

[<- Previous Step](https://bedwards254.github.io/testBDBC/jekyll/2019/01/22/KryFlux.html)
[Next Step ->](https://bedwards254.github.io/testBDBC/jekyll/2019/01/22/fiwalk.html)
[Home](https://bedwards254.github.io/testBDBC/jekyll/2019/01/23/welcome-BDBC.html)
