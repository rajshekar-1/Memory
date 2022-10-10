# MultiBoot
## Refind - Bootloader

Documentation: [Refind  Docs](https://www.rodsbooks.com/refind/)

## How this works

> 	Windows            Ubuntu        Arch        MacOS
> > 		 Grub            Refind         clover 
> > > 					BIOS

From above you can see that Grub, Refind, Clover are all independent of the installed OS 
You can boot to any OS from any supported bootloader.

They dont change when you install new OS. 
None of the Operating systems i have tried use refind. They all use grub or some alternative. So its safe to assume that refind will remain untouched by your installations. 

>If your OS distrubution uses ReFind pay attention to what you do.

So if your OS breaks and messes up your grub or any other bootloader you can thoeretically boot to refind and boot or install any OS you need. 

## Why refind?
refind detects bootable partitions and allows you to boot from it. 
- You can make a FAT32 partition of 10-15GB. Extract your ISO to that partition and you can boot from it. No need for slow USB or tools to make bootable drives
	-  FAT32 does not support individual files larger than 4GB.  So if you extract an ISO. And one of the files is larger than 4 GB you cant move that file to FAT32 partition.
	- If your ISO is larger than 4GB there are no problems but if one of the extracted individual file is larger than 4 GB than you have issues.
	> 	Windows 11 has this issue where one of the files inside the ISO is more than 4 GB. 

> Use any linux distro or windows 10 to make a normal bootable USB and install windows 11 

- exFAT doesnt have this issue but I had situations where files would go missing between reboots. So use at your own risk to have windows on backup

TLDR: You can have multiple partitions with various ISOs extracted and boot from any of them easily.   

## steps

1. Run CMD as Administrator
   - Powershell and other shells can lead to errors. 

2. Download and extract refind windows archive to a directory and cd into that directory

```
	cd /Path/to/directory
```

3. Mount EFI partition
	- EFI partition contains all bootloader.  This persists over any OS installation. So unless that particular distro targets EFI, you will have refind to boot and recover any installations you have. 

	```
	mountvol R: /S
	```
	
	- R  - is your drive letter. 
	- /S  - is a flag for EFI partition

		After this step you have access to your EFI system like any other directory. So before making changes think twice.

4. If you followed step 2 properly you should be in the refind folder.
		- Change into the folder where you extracted ReFind, so that the `refind` folder is visible when you type dir. 

> you will be copying the `refind` folder  to location inside EFI partition so it is important that refind folder is visble when you type dir

5. Copy all the files from refind to EFI folder inside EFI partition

```bash
xcopy /E refind R:\EFI\refind\
```

7. Switch to EFI partiton and navigate to the refind folder you copied.
			`R:`  - switches you to EFI partition
			cd to refind
			rename our refind sample config to refind config	

```bash
	R:
	cd EFI\refind 
	rename refind.conf-sample refind.conf
```


> you can customise refind if you know what you are doing
> Do not change anything else


8. Now to switch your default bootmanager.  Paste this in Admin CMD prompt 

```bash
 bcdedit /set "{bootmgr}" path \EFI\refind\refind_x64.efi
```

9. Reboot to BIOS and check your default boot manager. 

	You should boot into  refind menu when you start your device

10. Boot into  windows

11. Use disk partition tool to shrink and make a FAT32 partition of 10gb+

12. Extract your prefered ISO into the partition. Dont keep it inside subfolders dump it all in root directory

13. Boot into refind and install your ISO.

> Sometimes you might need to rename the partition label to whatever OS you are installing.
> >EndeavourOS for example needs your partition name to be EOS-202209 or something similar. 
> You can rename it windows or during install. During such errors you get thrown into a shell. 
> 

 Your partition name will be New /volume or something you named it as. 

rename it using mv 

the name required will be a few line above in the error prompt. 
for endeavour OS its usually like cannot find /dev/disk/by-label/eos-202209

so i change New volume label to EOS_202209

```bash
mv New /volume EOS_202209 
```

That should fix it. 


