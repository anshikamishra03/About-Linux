# Disk and Storage Management in Linux

## Introduction to Disk and Storage Management

Managing disks and storage efficiently is crucial for system performance and stability. Linux provides various commands to monitor, partition, format, mount, and manage disk storage.

### Index of Commands Covered

#### Viewing Disk Information

1. lsblk – Display block devices

2. fdisk -l – List disk partitions

3. blkid – Show UUIDs of devices

4. df -h – Check disk space usage

5. du -sh /path – Show size of a directory

#### Partition Management

1. fdisk /dev/sdX – Create and manage partitions

2. parted /dev/sdX – Alternative to fdisk for GPT disks

3. mkfs.ext4 /dev/sdX1 – Format a partition as ext4

4. mkfs.xfs /dev/sdX1 – Format a partition as XFS

#### Mounting and Unmounting

1. mount /dev/sdX1 /mnt – Mount a partition

2. umount /mnt – Unmount a partition

3. mount -o remount,rw /mnt – Remount a partition as read-write

#### Logical Volume Management (LVM)

1. pvcreate /dev/sdX – Create a physical volume

2. vgcreate vg_name /dev/sdX – Create a volume group

3. lvcreate -L 10G -n lv_name vg_name – Create a logical volume

4. mkfs.ext4 /dev/vg_name/lv_name – Format an LVM partition

5. mount /dev/vg_name/lv_name /mnt – Mount an LVM partition

#### Swap Management

1. mkswap /dev/sdX – Create a swap partition

2. swapon /dev/sdX – Enable swap space

3. swapoff /dev/sdX – Disable swap space

#### Viewing Disk Information

##### Using lsblk

List all block devices:

```lsblk```

##### Using fdisk

View partition details:

```fdisk -l```

##### Using df

Check available disk space:

```df -h```

##### Using du

Find the size of a directory:

```du -sh /var/log```

#### Partition Management

##### Creating a Partition with fdisk

```fdisk /dev/sdX```

Follow the interactive prompts to create a partition.

##### Formatting a Partition

Format as ext4:

```mkfs.ext4 /dev/sdX1```

Format as XFS:

```mkfs.xfs /dev/sdX1```

#### Mounting and Unmounting

##### Mount a Partition

```mount /dev/sdX1 /mnt```

##### Unmount a Partition

```umount /mnt```

##### Remount a Partition

```mount -o remount,rw /mnt```

#### LVM Management

##### Create a Physical Volume

```pvcreate /dev/sdX```

##### Create a Volume Group

```vgcreate vg_name /dev/sdX```

##### Create a Logical Volume

```lvcreate -L 10G -n lv_name vg_name```

##### Format and Mount the Logical Volume

```
mkfs.ext4 /dev/vg_name/lv_name

mount /dev/vg_name/lv_name /mnt

```
#### Swap Management

##### Create a Swap Partition

```mkswap /dev/sdX```

##### Enable Swap

```swapon /dev/sdX```

##### Disable Swap

```swapoff /dev/sdX```
