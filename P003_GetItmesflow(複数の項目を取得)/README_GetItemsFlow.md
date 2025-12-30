---

#### **README_GetItemsFlow.md**

📌 **About This Repository**  
This repository provides a sample Power Automate flow to **retrieve multiple items from a SharePoint list**.  
It includes a ready-to-import ZIP file and sample data for beginners.  
Perfect for workflow automation and boosting productivity with low-code solutions.

---

## ✅ Features
- Built with Microsoft Power Automate
- Get multiple items from SharePoint list
- Understand JSON output structure
- No-code approach for business process automation

---

## 🚀 Flow Overview
- **Trigger**: Manual trigger
- **Actions**:
  1. SharePoint "Get items"
  2. Compose action to check JSON output
- **Goal**: Retrieve SharePoint list data in JSON format and learn how to use it in subsequent steps

---

## 📦 Download
- Flow ZIP: `/flows/P002_GetItemsSample.zip`
- Sample Excel: `/samples/sample_contract.xlsx`

---

## 🔧 Import Instructions
1. Go to Power Automate portal
2. Select **Import** from "Solutions" or "My flows"
3. Upload the ZIP file
4. Configure SharePoint connection
5. Save and you're ready!

---

## 🛠 Build from Scratch
- Add a manual trigger
- Add SharePoint "Get items" action
- Set the following expression in Compose:
```plaintext
outputs('Get_items')?['body/value']