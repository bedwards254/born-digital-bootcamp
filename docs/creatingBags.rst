.. _creatingBags:

========================================================
Packaging disk images and supplemental files using BagIt
========================================================

-----------------
Before you begin:
-----------------

* This workflow uses tools stored in Windows. If necessary, restart the Digital Archives Lab workstation and boot to the Windows hard drive. You can find instructions on how to do this :ref:`here <BC_Windows>`.
* Ensure that the Digital Archives Lab workstation is not connected to the Internet by unplugging the ethernet cable.

---------------
Create folders:
---------------

1. Ensure that the Digital Archives hard drive dock is powered on. 

**NOTE:** Before beginning the process of creating bags, each forensically packaged disk image (.E01) must be placed with any supplemental files inside a folder named using the MSSnumber_ID (e.g., 1297_01). There are two ways to create these folders:

*Option 1*
	a. Navigate to your disk image files on the Digital Archives hard drive dock. 
	b. Create each folder one-by-one by right-clicking and selecting **New Folder**. 
	c. Name each folder using the MSSnumber_ID.

*Option 2*
	a. Type ``cmd`` into the Windows Search Box to open a terminal window. 
	b. Type the following command into the terminal window in order to navigate to the **Mackey_diskImages** folder on the Digital Archives hard drive dock and hit **enter**:

::

	cd D:/DigitalArchives/diskImages/Mackey_diskImages
	
c. Type the following command to create all 20 folders at once and hit **enter**:

::

	mkdir 1297_{[ID]..[ID]}
	
*For example*::

	mkdir 1297_{150..170}
	
2. Each folder needs to contain the following files:
	a. The forensically packaged disk image (.E01)
	b. The ``imgMD5.txt`` file created during migration from a ``.img`` file to a ``.E01`` file
	c. The ``verify[MSSnumber_ID].txt`` file also created during migration from a ``.img`` file to a ``.E01`` file (e.g., ``verify1297_24.txt``)
	d. The ``fiwalk.xml`` file
	
You can either copy and paste the relevant files into their folder or use the command line to move files (instructions forthcoming).

------------
Create a Bag:
------------

3. If you don't already have a terminal window open, type ``cmd`` into the Windows Search Box to open one.
4. Type the following command into the terminal window in order to package your first disk image folder as a Bag and hit **enter**:

::

	bagit.py --md5 --sha1 --contact-name=[your netID] 	
	D:\DigitalArchives\diskImages\Mackey_diskImages\
	[MSSnumber_ID]
	
*For example*::

	bagit.py --md5 --sha1 --contact-name=[netID] 	
	D:\DigitalArchives\diskImages\Mackey_diskImages\
	1297_173
	
5. Wait for a confirmation message that Bag creation is complete.

-----------------
Validate the Bag:
-----------------

6. Type the following command in order to ensure that the newly created Bag is valid and hit **enter**:

::

	bagit.py --validate D:\DigitalArchives\diskImages\
	Mackey_diskImages\[MSSnumber_ID]
	
*For example*::

	bagit.py --validate D:\DigitalArchives\diskImages\
	Mackey_diskImages\1297_173
	
7. Wait for a confirmation message that the Bag is valid.

-----------------------------
Repeat for remaining folders:
-----------------------------

8. For all remaining folders, repeat from step 4.

**Time-saving tip:** Use the up arrow to page through commands that you have previously run in the terminal window. Once you have found the correct command, you can edit it as needed before running it again.