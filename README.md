Runkeeper2Endomondo
-------------------
Bulk import RunKeeper or Sports Tracker GPX files into Endomondo 

Description
-----------
This tool takes all of the unzipped GPX files from a RunKeeper or Sports Tracker export and concatenates them into one large GPX file which can be imported into Endomondo.

There are two versions - [1] a simple Python cli script which you run from the directory with the GPX files and [2] a simple Windows Python GUI which you can run from anywhere.

More details over on http://conoroneill.net/a-simple-tool-to-bulk-import-your-runkeeper-data-into-endomondo/

Exporting from RunKeeper
------------------------
* You export from RunKeeper as follows:
    * Click on your name in the top right of the main screen
    * Select My Settings
    * Scroll down and you'll see a small blue link on the bottom left to "Export Data"
    * Click that and follow the instructions
    * When you get the ZIP file from RunKeeper, unzip it into its own directory
	* You should now have a directory containing a bunch of GPX files

Exporting from Sports Tracker
-----------------------------
* I don't know. Can someone give me the instructions for this.
	
Python Windows Version for End-Users
------------------------------------
* You convert to Endomondo as follows:
    * This is a Windows Executable. You don't know me from Adam. Please run a virus checker on it after you download.
    * Run runkeeper2endomondogui.exe
    * If Windows 8 gives you a protection warning, click "More Info" and then "Run Anyway"	
	* Use the File menu to select the directory with all of your GPX files
    * Currently the import only does GPX files. So it is missing any manually entered treadmill runs etc.
    * The code is very rough and may show "not responding" as it grinds through larger files. It tells you what it is doing in the main window so just be a bit patient, particularly if you have an older PC.
	* When it is done, you will now have a file called endomondo.gpx in the same directory as your other GPX files
    * I've read that Endomodo craps-out on files over 10MB, so if the endomondo.gpx file is bigger than that, you'll have to do this process in batches with sub-sets of the GPX files. As a guide, my 47 GPX files including several half marathons and a full marathon come in at 4MB.

Importing into Endomondo
------------------------
* You import into Endomondo as follows:
	* Once my tool is done, go to Endomondo and select "New Workout"
	* Select the "Import from File" option
	* Point it to the endomondo.gpx file
    * Endomondo will appear to hang when you do the import. Leave it running and then open another browser tab and check your activity history. When it is fully populated with the imported activities, you can then safely close the original browser tab.
	* That's it, you're done

	
Python CLI Version for Developers
---------------------------------
* Install the following: 
    * Python 2.7 (I use 32-bit Activestate Python on 64-bit Windows 8)
	* BeautifulSoup
* Put runkeeper2endomondo.py in the same directory as the GPX files
* Open a command prompt
* python runkeeper2endomondo.py
* It outputs endomondo.gpx in the same directory


Python Windows Version for Developers
------------------------------------
* Install the following:
    * Python 2.7 (I use 32-bit Activestate Python on 64-bit Windows 8)
	* BeautifulSoup
	* PySide (http://qt-project.org/wiki/PySide)
* Download PyInstaller (http://www.pyinstaller.org) and unzip into a directory
* Copy runkeeper2endomondogui.py into the PyInstaller directory
* Generate a standalone exe using this:   python pyinstaller.py -F -w runkeeper2endomondogui.py
* The exe is then in the runkeeper2endomondogui\dist sub-directory


Changelog
=========

2013/03/12
----------
First rough version. Tested on 47 RunKeeper GPX files including several Half Marathons and one Marathon. Quite slow. 

2013/08/17
----------
Tiny change to work with the Sports Tracker timestamp format. Seems to work on sample files provided by a kind reader of my blog. Would love to hear more confirmation.

2013/10/14
----------
Another simple change to work with a variation of the Sports Tracker timestamp format.

