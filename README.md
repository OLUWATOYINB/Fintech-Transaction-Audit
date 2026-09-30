# Fintech Transaction Dispute & Operations Audit (Excel Project)

## Project Overview
This project focuses on auditing 100 high-volume digital wallet transaction records using Microsoft Excel. The goal is to standardize messy customer strings, verify data completeness, isolate platform failure rates, and uncover backend system bugs to optimize desk-bound support workloads.

## Excel Toolkit Applied
* **Data Cleaning:** Standardized mixed-case text strings using the `=PROPER()` function.
* **Data Integrity Auditing:** Implemented the `=COUNTBLANK()` function across named columns to verify a 100% complete dataset with zero missing rows.
* **Advanced Aggregations:** Structured multi-conditional `=COUNTIFS()` table parameters to track channel failure frequencies.
* **Business Intelligence Reporting:** Built separate, organized reporting sheets (**Management_Dashboard** and **Fintech_Transaction_Analysis_Wo**) using interactive **Pivot Tables** to aggregate currency metrics and filter transaction states.

---

## Diagnostic Questions & Tactical Solutions Resolved

### 🧠 Question 1: How do we fix inconsistent text data to prevent mathematical calculation errors?
* **The Solution:** Identified that customer names and location fields contained messy, mixed-case formatting. Inserted clean columns using `=PROPER(B2)` and `=PROPER(C2)` to standardize all 100 rows. Applied 'Paste as Values' to permanently lock the text data as pure text strings, and safely deleted the original uncleaned columns to keep the database compact and professional.

### 🧠 Question 2: Exactly how many failed transactions occurred specifically on the Mobile App channel?
* **The Solution:** Converted the clean data array into an official Excel Table (`Ctrl + T`) to unlock column-header referencing. Wrote a multi-conditional `=COUNTIFS(Table1[Channel], "Mobile App", Table1[Status], "Failed")` formula to scan all 100 transaction rows, successfully pinpointing the exact failure frequency.

### 🧠 Question 3: How do we visually track total financial transaction volume and isolate backend software bugs for executives?
* **The Solution:** Created two dedicated, clean worksheet reporting pages to separate data logs from analytics:
  1. **Management_Dashboard Sheet:** Built a Pivot Table placing `Clean_Location` in the Rows box and `Amount_Naira` in the Values box to automatically sum and display total transaction metrics across Lagos, Ibadan, Abuja, and Kano side-by-side without manual math.
  2. **Fintech_Transaction_Analysis_Wo:** Built a targeted Pivot Table filtering the payment status exclusively to `Failed`. Discovered a 100% data correlation where every single failed transaction forced a 'Yes' flag in the dispute log (causing the 'No' column to completely disappear). This mathematically proved a critical system bug: our app fails to auto-refund failed payments, directly overloading inbound customer service desks with manual complaints.
