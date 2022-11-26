---
layout: default
title: Disk Commands
parent: Linux
nav_order: 1
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