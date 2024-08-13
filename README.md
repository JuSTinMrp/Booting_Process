# COMPLETE DOCUMENTATION FOR BOOTING PROCESS - personal usage

## Checking the Bitlocker Status
```
manage-bde -status
manage-bde -protectors -disable C:.
```



## Converting Normal Pendrive to Bootable Pendrive
Use `rufus` - [Click Here](https://rufus.ie/downloads/)

## Converting Bootable Pendrive to Normal Pendrive
Open and Run command prompt as administrator
```
$ diskpart
$ list disk
$ select disk <no_of_disk>
$ clean
$ create partition primary
$ format fs=fat32 quick                 #if the storage is <=32GB
```
