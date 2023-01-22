---
layout: default
title: Disk Commands
parent: Linux
nav_order: 2
---
### Disk commnads

Filling the second partition on the /dev/sda disk with all zeros  
```dd if=/dev/zero of=/dev/sdX2 bs=1M``` replace X with the target drive letter.  
Filling the third partition with random data  
```dd if=/dev/urandom of=/dev/sdX3 bs=1M``` #replace X with the target drive letter.  
Wipe your master boot record (MBR)  
```dd if=/dev/zero of=/dev/hdX bs=446 count=1``` #replace X with the target drive letter.  
Filling the disk with all zeros (This may take a while, as it is making every bit of data 0)  
```dd if=/dev/zero of=/dev/sdX bs=1M```replace X with the target drive letter.  
Filling the disk with random data rather than zeros   
```dd if=/dev/urandom of=/dev/sdX bs=1M``` replace X with the target drive letter   
Display a list containing file system information  
```lsblk -f```   
Format a disk partition with the ext4 file system  
```sudo mkfs -t ext4 /dev/sdb1```   
Mount the partition to the data directory  
```sudo mount -t auto /dev/sdb1 /mnt/data```   
Copy file to partition ( bootable usb )      
```sudo dd bs=4M if=Downloads/distro-image.iso of=/dev/sdb conv=fdatasync status=progress```    
Format a drive ( make sure to umount before )       
```sudo mkfs.ext4 /dev/sdb1```  
