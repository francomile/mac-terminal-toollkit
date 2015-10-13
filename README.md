# Mac OS X Terminal toolkit
---
<br>

### Create a _bootable_ usb stick with dd command	

```shell
$ hdiutil convert -format UDRW -o ~/Desktop/target.img ~/Desktop/ubuntu.iso
$ diskutil list
$ diskutil unmountDisk /dev/disk1
$ sudo dd if=/Users/username/Desktop/ubuntu.img.dmg of=/dev/rdisk1 bs=1m
$ diskutil eject /dev/disk1

```

---
### Speed up keyboard repetition.	

`defaults write -g ApplePressAndHoldEnabled -bool false`	
### Define the desired repetition speed => 0 1 2 3 less is faster=(0) Set it really fast:
`defaults write NSGlobalDomain KeyRepeat -int 0.02`	
### Set a shirt delay until keypressed => less is faster (don't put it under 7 or you won't be able to write properly):		
`defaults write NSGlobalDomain InitialKeyRepeat -int 12`

---
### Fix the "no connected camera" error in your mac.

```shell
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

		
---
### Scan your local wireless environment from the command line. 

Note that if you're running **El Capitan** you'll have to disable **System Integrity Protection** to make the symlink to `/usr/sbin`.	

```shell
$ sudo ln -s /System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport /usr/sbin/airport 
$ aiport -s
```
For convenience, you can add an alias to your `.bash_profile` or `.zshrc` like the following.	

```shell
alias wifiscan='airport -s'
```	

---
### Increase Window resize speed for Cocoa apps.	
`defaults write NSGlobalDomain NSWindowResizeTime -float 0.001` 	

---
### Disable Warning when changing file extension.	
`defaults write com.apple.finder FXEnableExtensionChangeWarning -bool false`	

---
### Show hidden `~/Library` folder.
`chflags nohidden ~/Library`	

### Allow quitting Finder via ⌘ + Q; doing so will also hide desktop icons"	
`defaults write com.apple.finder QuitMenuItem -bool true`

 
