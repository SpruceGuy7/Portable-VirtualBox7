To build Portable-VirtualBox7 from source do the following:

### Prerequisites

Obtain and install the following free tools

* AutoIt version 3.3.8.1 from https://www.autoitscript.com/autoit3/files/archive/autoit/autoit-v3.3.8.1-setup.exe
* 7zip from http://www.7-zip.org/
* Resource Hacker from http://www.angusj.com/resourcehacker/

## Obtaining the source code

Check out the source code from GitHub. For example by using [GitHub on Windows](http://windows.github.com/) or use `git` from the command line like this:

`git clone https://github.com/vboxme/Portable-VirtualBox7.git`

This will create a new folder named `Portable-VirtualBox7`.

## Making a new version with the build script

Run the `build.bat` script. The new version should appear in the `build\release` directory.

## Making a new version manually

### Compiling manually

1. Go to the Start menu and select `All programs` -> `AutoIt v3` -> `Compile Script to .exe (x86)`
2. Use the browse functionality to set:
  * Source: `Portable-VirtualBox7\source\Portable-VirtualBox7.au3`
  * Destination: `Portable-VirtualBox7\Portable-VirtualBox7.exe`
  * Custom Icon: `Portable-VirtualBox7\source\VirtualBox.ico`
3. Click `Convert`

A new `.exe` file is created as `Portable-VirtualBox7.exe`. This is Portable-VirtualBox7 and can be run from the Portable-VirtualBox7 folder.

### Releasing manually

To make a release you also need to do the following:

1. If you have run it in the Portable-VirtualBox7 folder delete the Portable-VirtualBox7 folder and do a new git clone and compile so its no junk in the data and app folders from previous runs
2. Go back to the Portable-VirtualBox7 folder
3. Right click on it and select `7zip` -> `Add to archive`
4. In the 7zip dialog select `Self extracting archive (SFX)` and click `OK` 
5. This will make a new `.exe` file named `Portable-VirtualBox7.exe`
6. Open the newly created `Portable-VirtualBox7.exe` with Resource Hacker find the Icon Group->1->1033
7. Use the Replace resource function to replace it with the icon at `Portable-VirtualBox7\source\VirtualBox.ico`
8. Save & exit

### AutoIt version when distributing software

Portable-VirtualBox7 uses a great and powerful scripting language known as AutoIt. Unfortunately some virus creators also use AutoIt with malicious intent. Each time a new version of AutoIt is released some virus is quickly written in it, and some anti-virus vendor then manages to marks sets of instructions found in all AutoIt made software as malicious. This causes many legitimate programs to be accidently flagged as viruses (this is what is known as a [false positive](https://en.wikipedia.org/wiki/Antivirus_software#Problems_caused_by_false_positives)).

Eventually software makers complain and the anti-virus maker realize there mistakes. AutoIt gets cleared again. However this vicious cycle means that if you do not want to get any falsely virus warnings when distributing software that you have built it is best to use an older version of AutoIt. We recommend version 3.3.8.1 that was released in November 2012. 

However if you for some reason want to use the newest version you can download it from http://www.autoitscript.com/site/autoit/downloads/ ( you need "AutoIt Full Installation" ).
