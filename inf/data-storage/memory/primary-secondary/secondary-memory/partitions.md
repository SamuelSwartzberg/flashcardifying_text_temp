# partitions

A secondary memory device is divided into n partitions.
How partitions are layed out on a secondary memory device is described by the partition table.
in the past, the MBR would have also included a partition table.
the MBR partition table was limited to 64 byte, which allowed for up to four partitions.
Today, partition tables are generally GPT, since MBR was limited to addressing 2 TiB drives.
GPT  GUID Partition Table
GUID in GUID Partition Table  globally unique identifier

gparted and gnome-disks are GUIs for partition/disk management

mac

On mac, ⟮drutil⟯ is the ⟮CLI⟯ utility for ⟮interacting with burnable media⟯. 
On mac, ⟮diskutil⟯ is the ⟮CLI⟯ utility for ⟮interacting with harddrives.⟯ 

Verb|Function|Which of drutil/diskutil?
⟮list⟯|⟮list attached devices⟯|⟮drutil, diskutil⟯
⟮eject⟯|⟮ejecting a device⟯|⟮drutil, diskutil⟯