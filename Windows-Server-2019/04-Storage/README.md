# Windows Server Storage Lab (Disk Management)

## Lab Overview

In this lab, I configured and tested different Windows Server storage types by adding multiple virtual disks to my Windows Server 2019 VM.

The objective was to understand:

- MBR partitioning
- Primary and Extended partitions
- Dynamic disks
- Spanned volumes
- Mirrored volumes (RAID 1)
- RAID-5 volumes

---

## Environment

- Platform: VMware Workstation
- Server OS: Windows Server 2019
- Tool Used: Computer Management → Disk Management

---

## 1️⃣ MBR – Primary & Extended Partition

I initialized a new disk using **MBR (Master Boot Record)**.

Then I:

- Created a Primary partition
- Created an Extended partition
- Created a Logical drive inside the Extended partition

This demonstrates understanding of classic MBR partition structure and logical drive hierarchy.

📸 Screenshot:

![MBR Primary Extended](Screenshots/mbr-primary-extended.png)

---

## 2️⃣ Spanned Volume

I converted the disks from **Basic → Dynamic** in order to use advanced volume types.

Then I created a **Spanned Volume** across multiple disks.

Characteristics:
- Combines free space from multiple disks
- Increases total storage capacity
- No fault tolerance (if one disk fails, all data is lost)

📸 Screenshot:

![Spanned Volume](Screenshots/spanned-volume.png)

---

## 3️⃣ Mirrored Volume (RAID 1)

I created a **Mirrored Volume** using two dynamic disks.

Characteristics:
- Data is written to both disks
- Provides redundancy
- If one disk fails, the other continues functioning

📸 Screenshot:

![Mirrored Volume](Screenshots/mirrored-volume.png)

---

## 4️⃣ RAID-5 Volume (3 Disks)

I created a **RAID-5 Volume** using three dynamic disks.

Characteristics:
- Data is striped across disks
- Parity information is distributed
- Can tolerate one disk failure
- Requires minimum 3 disks

This RAID-5 volume will be used in the next lab as a dedicated **File Server data volume**.

📸 Screenshot:

![RAID-5 Volume](Screenshots/raid5-volume.png)

---

## Key Skills Demonstrated

- Disk initialization (MBR)
- Primary vs Extended partition design
- Dynamic disk configuration
- RAID implementation in Windows Server
- Storage planning for enterprise environments
- Preparation for File Server deployment

---

## Next Step

Next lab: Configure the RAID-5 volume as a File Server with:
- Shared folders
- NTFS permissions
- Share permissions
- Access testing from domain users

