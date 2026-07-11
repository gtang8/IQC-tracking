#
[中文](./readme_cn.md) / [Tiếng Việt](./readme_vn.md) 

---

# 📘 Mattel IQC Incoming Material Testing and Tracking System Standard Operating Procedure

This system utilizes a "Dual-Role Physical Isolation" and "Offline File Relay" workflow. The **IQC Inspector** and **Quality Supervisor** operate independently on their own computers, using JSON file exports and imports to relay documents and merge data seamlessly.

---

## 👨‍🔧 Part 1: IQC Inspector Guide (Entry, Chem Update & Physical Test)

### Step 1: Incoming Material Entry & [Chem Test Frequency] Smart Judgment

1. Open the system page and fill in the delivery details in the **[1. New Incoming Batch Entry & Smart Interception Judgment]** section.
2. **Quick Entry:** When you type the "Supplier Code" or "Supplier Name", the system will auto-match and populate the corresponding "Mattel Supplier Level".
3. Select the "Material Category" and "Material Sub-Category" sequentially.
4. Once filled, a **Traffic Light Judgment** for Chemical Testing will appear at the bottom:
* 🚨 **Red Badge (Must Test):** Indicates the material has reached its testing cycle (e.g., 6/12 months expired), or it is a mandatory per-batch test for unassigned suppliers.
* 🔒 **Green Badge (No Test Needed):** Indicates the chemical test is still valid. The system locks the input fields and auto-fills the date and report number of the last valid chemical report.


5. Confirm the details and click **[💾 Save Batch to DB]** (保存批次入库). The record will automatically move to the Management Ledger below.

### Step 2: Quick Update for [Chemical Test] Reports

In practice, red-badged "Must Test" materials often arrive before the lab issues the chemical report. The system allows quick inline updates directly in the ledger:

1. Once the lab issues the chemical report, locate the batch in the ledger.
2. **Double-click** the **[Chem Report Date]** cell. A calendar picker will appear; select the date and press `Enter` to save.
3. **Double-click** the **[Test Report No.]** cell. Type the report number (e.g., C-2026-XXXX) and press `Enter` to save.
4. *Smart Sync Tip: If subsequent batches of this material arrive, updating the main batch's chemical report will automatically sync and lock the subsequent records. No duplicate entry is required.*

### Step 3: [Physical Test] Data Entry & Preliminary Judgment

1. In the ledger, click the **[⏳ Pending]** (待检验) button on the far right of the relevant record to open the Physical Inspection window.
2. The system **automatically loads the corresponding inspection items and standard specifications** based on the Material Sub-Category you selected.
3. Row by row, input the "Sample Qty", "Fail Qty", and "Actual Data/Remarks".
* *Poka-Yoke Tip: After inputting "Ac" (Acceptance number) at the top, the system automatically calculates "Re" (Rejection number).*


4. Scroll down to the **[📊 Inspector Preliminary Judgment]** section and select the result (Pass / Fail).
5. Add any on-site abnormalities or descriptions in the **[📝 Inspector Notes]** box at the bottom.
6. Click **[💾 Save Data Only]** at the bottom. The ledger status will change to a grey-blue `[⏳ Pending Approval]`.

### Step 4: Package & Send for Approval (To Supervisor)

After inspecting a batch of materials, you must send the data to the Supervisor for approval:

1. Check the box on the left side of the ledger for the records you want to send (you can select multiple).
2. Click the **[📤 Extract/Export [Selected Rows JSON] for Collaboration]** button above the ledger.
3. The system will download a file named `待批准-YYYYMMDD-HHMMSS.json` (Pending Approval-Date-Time).
4. Send this JSON file to the Quality Supervisor via WeChat, DingTalk, or Email.

### Step 5: Receive Approval & Print Report

1. Once you receive the approved file back from the Supervisor, click **[📥 Smart Import/Merge JSON]** at the top right of the page and select the file.
2. The system will seamlessly merge the approval results into your ledger without overwriting original data. The record status will turn green and display `[✅ Approved]`.
3. Double-click the ledger to open the physical inspection window for that record, scroll to the bottom, and click **[🖨️ Print Final Approval Report (In PDF)]**.
* *Printing Tip: The layout is strictly locked by the system. The Inspector Notes box is fixed at a standard 8-line height to prevent formatting distortion. The generated PDF will automatically be named after the physical report number.*



---

## 👨‍💼 Part 2: Quality Supervisor Guide (Approval & Return)

Supervisors must approve documents in the dedicated "Supervisor Mode" to unlock maximum editing and printing permissions.

### Step 1: Unlock Hidden Supervisor Mode

1. Upon opening the system, move your cursor to the main title at the top center: **"美泰 IQC 进料检验与追踪系统"**.
2. **Double-click** the title quickly. An authentication prompt will appear.
3. Enter the Supervisor password: `ABC123456`, and click OK.
4. Upon successful authentication, a red `[Supervisor Mode Activated]` badge will appear next to the title, indicating that your approval and printing permissions are fully unlocked.

### Step 2: Import & Review Inspection Records

1. Upon receiving the `待批准-xxx.json` (Pending Approval) file from the Inspector, click **[📥 Smart Import/Merge JSON]** at the top right to load it.
2. Locate the records marked as `[⏳ Pending Approval]` in the ledger and click them to open the Physical Inspection window.
3. Verify that the Chemical Test report information is complete, and review the physical test data, preliminary judgment, and inspector notes.

### Step 3: Add Comments & Approve

1. Scroll to the green area at the bottom: **[✍️ IQC Supervisor Final Approval Area]**.
2. In the **[Approval Notes]** box, type your review comments, AOD (Accept on Deviation) reasons, or return instructions (this box is placed at the top of the section for easier long-text entry).
3. Select the **[Approval Conclusion]** below (Approved / AOD / Rejected).
4. Confirm the **[Supervisor Signature]** (QC Supervisor / QA Manager) and **[Approval Date]**.
5. Click **[💾 Save Data Only]** at the bottom to finalize the approval.

### Step 4: Return Approved Data

1. In the ledger, check the boxes for the records you just approved (status will now be green `[✅ Approved]`).
2. Click the **[📤 Extract/Export [Selected Rows JSON] for Collaboration]** button above the ledger.
3. The system will auto-download a file named `已批准-YYYYMMDD-HHMMSS.json` (Approved-Date-Time).
4. Send this file back to the Inspector via WeChat or Email. The Inspector will import it to close the loop.

### Step 5: Full Disaster Recovery Backup (Weekly Task)

To prevent data loss due to accidental browser cache clears, the Supervisor should perform a full system backup regularly:

1. Click the **[📤 Export JSON Backup]** button at the top right of the page.
2. The system will download a master file containing the entire ledger history, all records, and the supplier database, named `Mattel_Integrated_DB_Backup_YYYYMMDD_HHMMSS.json`.
3. Store this file on a secure company network drive or encrypted USB. If a computer is replaced, importing this file into a blank system will instantly restore 100% of your data.
