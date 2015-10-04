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

---
### Speed up keyboard repetition.	

`defaults write -g ApplePressAndHoldEnabled -bool false`	
### Define the desired repetition speed => 0 1 2 3 faster=(0).
`defaults write NSGlobalDomain KeyRepeat -int 0`

---
### Fix the "no connected camera" error in your mac.

```
sudo killall VDCAssistant		
sudo killall AppleCameraAssistant
```		

---
### Encrypt some file with openssl.	

`openssl enc -aes-256-cbc -salt -in file.txt -out file.txt.enc`

### Decrypt it back.

`openssl enc -aes-256-cbc -d -in file.txt.enc -out file.txt` 

	
---		

### Disable 'System Integrity Protection' on Mac OS X **El Capitan**.	

1. Restart your Mac.
2. Before OS X starts up, hold down `Command-R` and keep it held down until you see an Apple icon and a progress bar. Release. This boots you into Recovery.
3. From the Utilities menu, select Terminal.
4. At the prompt type exactly the following and then press Return: `csrutil disable`.
5. Terminal should display a message that SIP was disabled.
6. From the  menu, select Restart.	

You can re-enable **System Integrity Protection** by folowing the above steps, but using `csrutil enable` instead.



