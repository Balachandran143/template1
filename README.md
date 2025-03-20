# File_Recovery-using-Autopsy

## Aim
The objective of this guide is to demonstrate how to:  
 - Create a **Virtual Hard Disk (VHD)**.  
 - Add images to the disk, delete them, and recover them using **Autopsy**.  
 - Understand the forensic recovery process for deleted files.  
 - Learn how to remove the virtual disk after completing the experiment.

## Virtual Disk Creation & File Recovery using Autopsy 


## Step 1: 
   Create a Virtual Hard Disk (VHD) 

### **1. Open Disk Management**  
- Press **Windows + X** → Click **Disk Management** 

 ![Screenshot 2025-03-20 140749](https://github.com/user-attachments/assets/912d6f84-620b-4190-900a-0042a2601e94)


### **2. Create a New VHD**  
- Click **Action** (top menu) → **Create VHD**.  
![Screenshot 2025-03-20 140950](https://github.com/user-attachments/assets/9d5a917b-cdbc-42e7-a8bf-f612cce8cc0a)

### **3. Choose File Location & Size**  
- Click **Browse** and select where to save the VHD file (e.g, `C:\new VHD.vhd`)
- Set the **size** (e.g: `1GB`) 
- Choose **VHD (Fixed Size)** and Click **OK**

![Screenshot 2025-03-20 141038](https://github.com/user-attachments/assets/27d2ec4f-4aa4-4e51-b65f-ec5509a1b27f)


### **4. Initialize the Disk**  
- In **Disk Management**, find your new disk (marked as "Not Initialized").  

![Screenshot 2025-03-20 144404](https://github.com/user-attachments/assets/a5b546f0-d2fc-40be-81ad-6b8647665844)

- Right-click the disk → Click **Initialize Disk**.

![Screenshot 2025-03-20 141106](https://github.com/user-attachments/assets/d71f975d-077c-4af6-8487-826eaef32449)


- Select **MBR (Master Boot Record)**. 

![Screenshot 2025-03-20 141127](https://github.com/user-attachments/assets/eb8cc265-0d63-4050-87a3-a53d2471472c)

### **6. Create & Format the Partition**  
- Right-click the **Unallocated Space** → Click **New Simple Volume**.
- ![Screenshot 2025-03-20 154441](https://github.com/user-attachments/assets/098f2ed4-6999-45fd-a96c-5e264d8fc2c6)
![Screenshot 2025-03-20 141152](https://github.com/user-attachments/assets/e6b5ad4c-dbb7-4491-a596-b2f3aa87a08b)
![Screenshot 2025-03-20 141200](https://github.com/user-attachments/assets/29ae3998-50e7-4de0-9269-dba5fdfd0053)

- Click **Next** → **Click on Mount in the following empty NTFS folder** → **Browse** → **Assign a drive letter (e.g., `C: or D:`)** → **New folder** → **OK**
![Screenshot 2025-03-20 141217](https://github.com/user-attachments/assets/4efdb455-89ac-45f2-b5d6-e714f102508b)
![Screenshot 2025-03-20 141225](https://github.com/user-attachments/assets/95444cb6-1475-4f22-aeb8-1fb1a1e4946e)
![Screenshot 2025-03-20 141309](https://github.com/user-attachments/assets/0e7be203-6025-4dc4-be9c-629f7bee9350)


- Click **next** → **Finish**. 

---

## **Step 2: Add & Delete Files for Recovery** 

### **1. Copy Files to the Virtual Disk**  
- Open **File Explorer** → Go to the new drive (`C: or D:`), where the folder created in the previous step
- Create a new folder (`TestFolder`) and copy **images or files** into it.  

### **2. Delete the Files**  
- Select any one or two images → Press **Delete**.  
- Empty the **Recycle Bin** to permanently delete them.  

---

## **Step 3: Recover Deleted Files Using Autopsy**  
### **1. Open Autopsy & Create a New Case** 

- Launch **Autopsy** and **Run as a administrator**  
- Click **Create New Case**.  

![Screenshot 2025-03-20 142228](https://github.com/user-attachments/assets/5dbfc32e-8830-4205-9b87-27e3173b4a71)

- Enter a **Case Name** (e.g., `Autopsy1`).  
- Choose a **Case Folder** location.  
- Click **Next** → Click **Finish**.  

![Screenshot 2025-03-20 142324](https://github.com/user-attachments/assets/fee1af9a-ebb6-4715-bcf2-6fdd86e8e825)

### **2. Add the Virtual Disk as an Evidence Source**  
- Click **Add Data Source**  → **Select Host**

![Screenshot 2025-03-20 142523](https://github.com/user-attachments/assets/11324f7f-0a32-4be6-91ed-dbc216cf8bc5)

- Select **Local Disk** → **next** 
![Screenshot 2025-03-20 142541](https://github.com/user-attachments/assets/8bf8c294-9b0b-4f2e-9111-b676a239bfa6)


- Select Disk → **Choose the VHD drive (`Drive1`)**
![Screenshot 2025-03-20 142638](https://github.com/user-attachments/assets/b472f62f-9dff-4402-8870-65f861855048)

- Click **Next** → Keep default settings → Click **Finish**.  
- Wait for Autopsy to process the disk.  

### **3. Recover Deleted Files**  
- Go to **File Views** (left panel).  

![Screenshot 2025-03-20 142746](https://github.com/user-attachments/assets/54778c0f-c712-46b3-b222-5aa40a0c6603)

- Click **Deleted Files** → Find your deleted images.  
- Right-click an image → Click **Extract File**.  

![Screenshot 2025-03-20 142824](https://github.com/user-attachments/assets/7534ff79-1c49-4693-91dd-66aafbf2aee5)

![Screenshot 2025-03-20 143045](https://github.com/user-attachments/assets/6a2cfda4-0863-4063-9df5-eb8e758a1f0f)


- Select a folder to see the recovered files (e.g., `C:\image_recovery`).  

**Your deleted images are now recovered!**  

---

## **Step 4: Delete the Virtual Disk (Optional Cleanup)** 

### **1. Detach the VHD**  
- Open **Disk Management** (`Win + X` → Disk Management).  
- Find the **virtual disk** (`C: or D:`).  
- Right-click the disk (not the partition) → Click **Detach VHD**.  

### **2. Delete the VHD File**  
- Open **File Explorer**.  
- Go to the location where you saved the `.vhd` file (e.g., `C:\new VHD.vhd`).  
- **Delete** the `.vhd` file.  
- Empty the **Recycle Bin**.  

**Your virtual disk is completely removed!**  
 
---
 

## Result :
 This guide covers creating a Virtual Hard Disk (VHD), adding, deleting, and recovering images using Autopsy, and safely deleting the virtual disk after the experiment.
