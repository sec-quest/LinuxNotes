# storage management
Not exhaustive list of useful commands, options, etc. \
</br>

### useful commands

lsblk&emsp;&emsp;&emsp;&emsp;shows partition structure of the disk \
blkid&emsp;&emsp;&emsp;&emsp;shows info about storage devices \
</br>
pvs&emsp;&emsp;&emsp;&emsp;shows all physical volumes \
vgs&emsp;&emsp;&emsp;&emsp;shows all volume groups \
lvs&emsp;&emsp;&emsp;&emsp;shows all logical volumes \
</br>



### most used partition types

**fdisk**&emsp;**gdisk** \
20&emsp;&emsp;8300&emsp;&emsp;linux filesystem \
19&emsp;&emsp;8200&emsp;&emsp;linux swap \
31&emsp;&emsp;8e00&emsp;&emsp;linux lvm \
</br>

### creating lvm

partitions in 'linux lvm' type \
pvcreate /dev/partition1 /dev/partition2 \
vgcreate -s 1M vgname /dev/partition1 /dev/partition2 \
&emsp;&emsp;&emsp;&emsp;-s 1M resizes default extent (4M) to 1M \
lvcreate -n lvname -L 1G vgname \ 
lvcreate -n lvname -l 80%FREE vgname \
lvcreate -s -n lvname-snap -l 10M /dev/vgname/lvname \
&emsp;&emsp;&emsp;&emsp;creates snapshot of lvname lvm \
</br>

