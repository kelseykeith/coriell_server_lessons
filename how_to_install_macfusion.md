# How to Install MacFusion

### Install All the Necessary Components

1. Install FUSE for macOS here: <https://osxfuse.github.io/>
2. Make sure you have XQuartz installed <https://www.xquartz.org/>
3. Make sure you have Homebrew installed <https://brew.sh/>
3. In terminal (you must have homebrew installed) `brew install caskroom/cask/macfusion-ng`

### Set Up

1. Create a folder on your laptop for the server to mount to, ex: `mkdir /Users/kelsey/Volumes`
2. Open macfusion.
3. Start the engine
4. Click on the plus sign in the lower left-hand corner and select SSHFS. 
5. Fill in your information
  - Under the SSH tab, add the host: 10.1.105.11, your user name, your password, and the path to your home directory /home/username
  - Don't change anything under the SSH Advanced Tab
  - Under the Macfusion tab, in the Mount Point box, add the absolute path to the folder you created in step 1, plus a unique name for the server, ex: /Users/kelsey/Volumes/coriell_kkeith. In the Volume Name box, put the same name as the name of the folder. I also suggest making sure the "Ignore Apple Double File" and the "Show in Finder Sidebar" boxes are check.
  - Click ok
6. Click the Mount button and you should be connected to the server.