# COMPLETE DOCUMENTATION FOR BOOTING PROCESS - personal usage


> **IMPORTANT**\
> This is a documentation for my personal use 



## Checking the Bitlocker Status
Type the following in command prompt
```
manage-bde -status                      :: Before Turning off Bitlocker
manage-bde -protectors -disable C:.
manage-bde -status                      :: After Turning off Bitlocker
```
<br>

## Converting Normal Pendrive to Bootable Pendrive
Use `rufus` - [Click Here](https://rufus.ie/downloads/)
<br>
<br>
## Converting Bootable Pendrive to Normal Pendrive
Open and Run command prompt as administrator
```
$ diskpart
$ list disk
$ select disk <no_of_disk>
$ clean
$ create partition primary
$ format fs=fat32 quick                 # if the storage is <=32GB
$ format fs=ntfs quick                  # if the storage is >32GB
```
<br>

## Snapshoting a pendrive into image
Try these cmds in linux terminal
```
$ lsblk
$ sudo dd if=/dev/sdX of=/path/to/backup.img bs=4M status=progress
$ sudo fdisk /dev/sdX            # d - delete until all partitions are done, w-write changes and exit
$ sudo mkfs.vfat -F 32 /dev/sdX1 # create partition
```
<br>

## Restoring img to pendrive
```
$ sudo dd if=/path/to/backup.img of=/dev/sdX bs=4M status=progress
$ lsblk
```
<br>

## SETEDIT Permission Grant
Connect your mobile phone using USB cable and Go to 
**`Developers Option -> Enable USB Debugging`**

1. Open **`command prompt`** or **`terminal`**
2. Type the following commands
```
$ adb devices -l
$ adb shell
$ pm grant by4a.setedit22 android.permission.WRITE_SECURE_SETTINGS
```

* [x] ref: [ADB Documentation][def]

[def]: https://developer.android.com/tools/adb
<!-- [def1]: <link_2> -->


<br>

