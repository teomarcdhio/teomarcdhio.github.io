---
layout: default
title: Mdadm raid
parent: Linux
nav_order: 3
---
### Linux Software raid setup with Mdadm

To setup a software raid wit mdadm you first need to make sure your drives are prepared and ready to be used.
Run ```fdisk /dev/sdb``` to setup your drive with the fdisk utility.   
Select n to create a new partition and proceed with the default values ( partition should be 1 and first and last sectors should be as per fdisk suggestion ).   
Use t to select the partition and define the partition type; select fd to set a Linux Raid Autoconnect type.   
Do the same for as many drives you need to add to the array.  
Install mdadm with ```sudo apt-get install mdadm```       
If the drive was previously used in an mdadm array, clean the super block with ```mdadm --zero-superblock /dev/sdb ``` 
To create the raid array use ```mdadm --create /dev/md0 --level=1 --raid-devices=2 /dev/sdb /dev/sdc``` where --level=1 represent the type of array you want to use ( 0 is stripe, 1 is mirror, etc ).   
Check the status of the array with ```cat /proc/mdstat```   
Format the newly created array with ```sudo mkfs.ext3 /dev/md0```   
Now, to mount your new device, create a directory ```mkdir /raid1``` and mount it with ```mount /dev/md0 /raid1```   
To validate that the raid is now mounted run ```df -H```; you shoudl now see your new /radi1 folder  
To make sure the raid is mounted automatically on boot use ```nano /etc/fstab``` add the following line ```/dev/md0 /raid1 ext3 noatime,rw 0 0```   
To check the array status ```cat /proc/mdstat```     
To get info on the array ```mdadm --query /dev/md0 or mdadm -D /dev/md0```   
If the array is degraded or only 1 drive available, you can remove a drive using ```sudo mdadm --remove /dev/md0 /dev/sdb``` and add a new one by ```sudo mdadm --add /dev/md0 /dev/sdb```     
To stop the array use ```mdadm --stop /dev/md0```    
To delete an array use ```mdadm --remove /dev/md0```     