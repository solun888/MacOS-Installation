# Rename volume name in startup manager


The Mac Startup Manager is stored in the firmware on the logic broad. The Mac Startup Manager reads the label to display from the same folder that the boot file is located. In the case of macOS, the boot file is named boot.efi and is located in the APFS volume named Preboot by default. Under macOS Monterey, this volume is protected by SIP. The label is stored as an image in the files name .disk_label and .disk_label_2x The file chosen by the firmware depends on the resolution of the display. Both files can be created by the bless command. A third file named .disk_label.contentDetails contains a text copy of the label. This file is not created by the bless command and is not used by the firmware.
Below is one possible procedure which can be use to change these files.

Restart to macOS Recovery, open a Terminal application window and enter the following command to disable SIP.
```shell
csrutil disable
```
Restart to macOS Monterey, open a Terminal application window and enter the following commands. These commands will change the Mac Startup Manager label for macOS Monterey to Macintosh HD . 

```shell
GROUP="$(diskutil info / | grep "APFS Volume Group")"
UUID="${GROUP##* }"
cd /System/Volumes/Preboot/$UUID/System/Library/CoreServices/
sudo bless --folder . --label "Macintosh HD"
printf "Macintosh HD" | sudo tee .disk_label.contentDetails; echo
sudo chgrp wheel .disk*
cd ~
```

Enter the following command to clear the SIP configuration.
```shell
sudo csrutil clear
```
Restart macOS Monterey. Upon restart, SIP will be enabled.

[Link](https://apple.stackexchange.com/questions/436980/rename-macos-monterey-disk-in-startup-manager)
