# **Lost Data Retrieval Report**

## **1. Introduction**

Data loss can occur due to accidental deletion, system crashes, malware, or hardware failures. Recovering important files is a critical task in digital forensics, IT maintenance, and personal data management. This project demonstrates a simple automated solution to retrieve lost or important files from a user’s system using Python.

## **2. Objective**

The goal of this task is to implement a Python-based program that scans a user’s directory, identifies important files based on their extensions, and copies them to a designated recovery folder. The project emphasizes practical understanding of file handling, automation, and basic data recovery techniques.

## **3. Tools and Technologies**

* **Programming Language:** Python
* **Libraries Used:**

  * `os` – for traversing directories and handling paths
  * `shutil` – for copying files
  * `tqdm` – for displaying progress bars
* **Supported File Types:** `.jpg`, `.png`, `.pdf`, `.txt`, `.docx`
* **Source Directory:** `C:/Users`
* **Recovery Directory:** `Recovered_Files`

## **4. Code Explanation**

The script performs the following key steps:

1. **Directory Setup:**

   * Creates a recovery folder (`Recovered_Files`) if it does not exist using:

     ```python
     makedirs(RECOVERY_DIR, exist_ok=True)
     

2. **File Collection:**

   * Recursively traverses the source directory (`C:/Users`) using `os.walk()`
   * Collects paths of all files in a list

3. **File Filtering and Copying:**

   * Checks each file’s extension against the defined list
   * Copies matching files to the recovery directory
   * Handles duplicate file names by appending a counter to avoid overwriting:

     ```python
     base, ext = os.path.splitext(file_name)
     while os.path.exists(dest_path):
         dest_path = os.path.join(RECOVERY_DIR, f"{base}_{count}{ext}")
         count += 1
     ```

4. **Progress Monitoring:**

   * Displays progress using `tqdm` for a better user experience

5. **Completion Notification:**

   * Prints a message when the recovery process is finished:

     ```python
     print("\n✅ Recovery Completed!")
     ```

## **5. Implementation Steps**

1. Install required library for progress bar:

   ```
   pip install tqdm
   ```
2. Save the script as `data_recovery.py`
3. Run the script in Python:

   ```
   python data_recovery.py
   ```
4. Wait for the scanning and recovery process to complete
5. Open the `Recovered_Files` folder to view all retrieved files

---

## **6. Results and Observations**

The program successfully identifies and copies all files with the specified extensions to the recovery directory. Duplicate files are renamed automatically to prevent data loss.

**Sample Observations:**

* Total files scanned: 10,000+ (example)
* Files recovered: 125 (.jpg, .pdf, .txt, etc.)
* Progress bar shows real-time scanning status
* Duplicate files are handled gracefully

## **8. Advantages and Limitations**

### **Advantages**

* Automates the data recovery process
* Supports multiple common file types
* Handles duplicate file names safely
* Provides real-time feedback with a progress bar

### **Limitations**

* Only recovers files from the existing directory (does not recover permanently deleted files)
* Does not recover files from damaged storage devices
* Limited to predefined extensions

---

## **9. Conclusion**

This project demonstrates an effective approach to recovering important files from a user’s system using Python. It emphasizes practical file handling, automation, and the importance of safeguarding data. Although limited to basic recovery, it provides a foundational understanding for more advanced data retrieval techniques.

---

## **10. Ethical Considerations**

This script should only be used on directories you have permission to access. Unauthorized access to other users’ files is illegal and unethical. Always ensure data privacy while performing recovery tasks.

---

