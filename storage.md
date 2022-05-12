## storage management
Not exhaustive, and still in build, list of useful commands, options, files, etc.


### useful commands

| **command** | **description** |
|-------------|-----------------|
| lsblk | shows partition structure of the disk |
| blkid | shows info about storage devices |
| pvs | shows all physical volumes |
| vgs | shows all volume groups |
| lvs | shows all logical volumes |



### most used partition types

| **mbr - fdisk** | **gpt - gdisk** | **type** |
|-----------|-----------|----------|
| 83 | 8300 | linux filesystem |
| 82 | 8200 | linux swap |
| 8e | 8e00 | linux LVM |
| fd | fd00 | linux RAID |


### creating lvm

- create partitions in 'linux LVM' type
- create physical volumes
```sh
pvcreate /dev/partition1 /dev/partition2
```
- create volume group with the name of vgname (-s 1M resizes default extent - 4M - to 1M) 
```sh
vgcreate -s 1M vgname /dev/partition1 /dev/partition2
```
- create logical volume with a name of `lvname` and a size of 1GiB or 80% of free space
```sh
lvcreate -n lvname -L 1G vgname
lvcreate -n lvname -l 80%FREE vgname
```
- create snapshot of given logical volume with a name of `lvname-snap` and size of 10MiB
```sh
lvcreate -s -n lvname-snap -l 10M /dev/vgname/lvname
```


