.. _creatingBags:

========================================================
Packaging disk images and supplemental files using BagIt
========================================================

-----------------
Before you begin:
-----------------

* This workflow uses tools stored in Windows. If necessary, restart the Digital Archives Lab workstation and boot to the Windows hard drive.
* Ensure that the Digital Archives Lab workstation is not connected to the Internet by unplugging the ethernet cable.

---------------
Create folders:
---------------

1. Ensure that the Digital Archives hard drive dock is powered on. 

**NOTE:** Before beginning the process of creating bags, each disk image must be placed inside a folder named using the MSSnumber_ID (e.g., 1297_01). There are two ways to do this:

*Option 1*
a. Navigate to your disk image files on the Digital Archives hard drive dock. 
b. Create each folder one-by-one by right-clicking and selecting **New Folder**. 
c. Name each folder using the MSSnumber_ID.

*Option 2*
	a. Type `cmd` into the Windows Search Box to open a terminal window. 
	b. Type the following command into the terminal window in order to navigate to your folder on the Digital Archives hard drive dock and hit **enter**:

::

	cd D:\DigitalArchives\diskImages\Mackey_diskImages\[your folder name]
	
	c. Type the following command to create all 20 folders at once and hit **enter**:

::

	mkdir 1297_{[ID]..[ID]}
	
*For example*::

	mkdir 1297_{150..170}
	
2. Copy each E01 disk image file into the correct folder.

------------
Create a Bag:
------------

3. If you don't already have a terminal window open, type `cmd` into the Windows Search Box to open one.
4. Type the following command into the terminal window in order to package your first disk image folder as a Bag and hit **enter**:

::

	bagit.py --md5 --sha1 --contact-name=[your name] D:\DigitalArchives\diskImages\Mackey_diskImages\[your folder name]\[MSSnumber_ID]
	
*For example*::

	bagit.py --md5 --sha1 --contact-name=dwaugh D:\DigitalArchives\diskImages\Mackey_diskImages\Waugh\1297_173
	
5. Wait for a confirmation message that Bag creation is complete.

-----------------
Validate the Bag:
-----------------

6. Type the following command in order to ensure that the newly created Bag is valid and hit **enter**:

::

	bagit.py --validate D:\DigitalArchives\diskImages\Mackey_diskImages\[your folder name]\[MSSnumber_ID]
	
*For example*::

	bagit.py --validate D:\DigitalArchives\diskImages\Mackey_diskImages\Waugh\1297_173
	
7. Wait for a confirmation message that the Bag is valid.

-----------------------------
Repeat for remaining folders:
-----------------------------

8. For all remaining folders, repeat from step 4.

**Time-saving tip:** Use the up arrow to page through commands that you have previously run in the terminal window. Once you have found the correct command, you can edit it as needed before running it again.