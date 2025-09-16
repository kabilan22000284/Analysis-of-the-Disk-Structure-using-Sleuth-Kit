# Analysis-of-the-Disk-Structure-using-Sleuth-Kit
## NAME: Kabilan V
## Reg no:212222100018
## AIM:
To analyze the disk structure of a given disk image using Sleuth Kit tools in Kali Linux.

## REQUIREMENTS
- **Operating System**: Windows 10/11 or Kali Linux
- **Tools**:  
  - [The Sleuth Kit for Windows](https://sleuthkit.org/)  
  - Optional GUI: [Autopsy Forensic Browser](https://www.autopsy.com/)
- **Test Data**: Disk image file (`disk.dd`, `disk.img`, `.E01`)

## ARCHITECTURE DIAGRAM
```mermaid
flowchart TD
    A[Disk Image / Physical Disk] --> B[mmls - Partition Analysis]
    B --> C[fsstat - File System Metadata]
    C --> D[fls - File Listing]
    D --> E[icat - File Recovery]
    E --> F[Recovered Data / Metadata Report]
```
## DESIGN STEPS:
### Step 1:
- Obtain or create a disk image file (e.g., disk.dd) to analyze.
- Open the terminal in Kali Linux.

### Step 2:
Use Sleuth Kit tools like:
 - mmls → Examine the partition layout.
 - fsstat → View file system details.
 - fls → Get file listing.
 - icat → Recover files using inode numbers.
### Step 3:
Interpret the output to understand:
 - Partition table layout
 - File system metadata (block size, creation time, etc.)
 - Deleted and allocated files
 - Inode-based file recovery

## PROGRAM:
Sleuth Kit Disk Analysis Commands
### Partition Analysis
```bash
mmls disk.dd
```
### File System Metadata
```bash
fsstat -o 2048 disk.dd
```
### File Listing
```bash
fls -o 2048 disk.dd
```
### File Recovery
```bash
icat -o 2048 disk.dd 4 > recovered_file.txt
```
- Recovers the file associated with inode 4.
## SAMPLE WORKFLOW (Windows)
```bash
# Step 1: View partitions
mmls.exe C:\forensics\disk.dd

# Step 2: View file system details
fsstat.exe -o 2048 C:\forensics\disk.dd

# Step 3: List files
fls.exe -r -o 2048 C:\forensics\disk.dd

# Step 4: Recover a file
icat.exe -o 2048 C:\forensics\disk.dd 6 > C:\forensics\image.jpg
```
## OUTPUT:

![435890092-48ad4510-e6d3-42cc-a6f7-a5453af7e6a9](https://github.com/user-attachments/assets/38402af4-39db-4a51-9518-573ca310c30a)


## Create Disk

![435590051-486b446a-0c92-4841-a095-3980000c3fc8](https://github.com/user-attachments/assets/8739f746-485b-4f73-a5af-31280b3cffa9)


## mmls

```
mmls disk.dd
```

## fls

```
fls -f fat -o 0 disk.dd
```

![435591750-85967a1e-38ab-4281-aa16-820b2cfa7479](https://github.com/user-attachments/assets/570ead96-1fd9-4834-ac98-42530ac39c43)

![435593232-36499cfc-15f3-4b86-8023-7876a2d5df25](https://github.com/user-attachments/assets/86d2a644-2f80-4428-85ec-2efc03e16702)

![435596459-1972eea0-f2aa-471e-8cc7-83e1279f38eb](https://github.com/user-attachments/assets/5dd5ec7d-f9f8-4475-a018-a4bef8cb4382)

![435593467-2f3834c6-b0da-45d9-a207-c1afc7937b3c](https://github.com/user-attachments/assets/83a87658-c58b-4a01-b492-91f5f57bfa86)






## RESULT:
The analysis was performed successfully using Sleuth Kit, and the disk structure was understood in detail.

## RESULT:
The analysis was performed successfully using Sleuth Kit, and the disk structure was understood in detail.
