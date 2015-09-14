# Mac OS X Terminal toolkit
---
<br>

### Create a _bootable_ usb stick with dd command	

```
$ hdiutil convert -format UDRW -o ~/Desktop/target.img ~/Desktop/ubuntu.iso
$ diskutil list
$ diskutil unmountDisk /dev/disk1
$ sudo dd if=/Users/username/Desktop/ubuntu.img.dmg of=/dev/rdisk1 bs=1m
$ diskutil eject /dev/disk1

```

<br>
---
### Speed up keyboard repetition	

`defaults write -g ApplePressAndHoldEnabled -bool false`	
### Define the desired repetition speed => 0 1 2 3 faster=(0)
`defaults write NSGlobalDomain KeyRepeat -int 0`

<br>
---
### Fix the "no connected camera" error in your mac

```
sudo killall VDCAssistant		
sudo killall AppleCameraAssistant
```		

<br>
---
### Encrypt some file with openssl		

`openssl enc -aes-256-cbc -salt -in file.txt -out file.txt.enc`

### Decrypt it back:

`openssl enc -aes-256-cbc -d -in file.txt.enc -out file.txt` 