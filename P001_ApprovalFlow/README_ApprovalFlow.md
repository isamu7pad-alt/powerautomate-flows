# K001_ApprovalFlow for Purchase Requests

## ✅ About This Repository
This repository demonstrates how to **automate a purchase request approval flow using Power Automate**.  
It integrates Microsoft Forms for request submission, sends approval requests, and notifies results in Microsoft Teams.  
A ready-to-use **flow.zip** file is provided for quick setup.

---

## 🚀 Features
- **Power Automate × Microsoft Forms × Microsoft Teams integration**
- **Streamlined approval workflow for business process improvement**
- **Low-Code approach for easy implementation**
- SEO keywords: Power Automate, workflow automation, low-code, RPA

---

## 📂 Flow Overview
- **Flow Name**: K001_ApprovalFlow  
- **What It Does**:
  - Collects requests via Microsoft Forms
  - Sends approval requests to approvers
  - Notifies results in Microsoft Teams

---

## 🔽 Download
- **Flow ZIP**: `./flows/K001_ApprovalFlow.zip`

---

## 🛠 Import Instructions
1. Go to Power Automate portal
2. Navigate to **Solutions → Import** and select the ZIP file
3. Configure connections (Forms, Approvals, Teams)
4. Save and enable the flow

---

## 🛠 Build from Scratch
Follow these steps if you prefer creating the flow manually.

### ✅ Step 1: Trigger
- **Connector**: Microsoft Forms  
- **Action**: When a new response is submitted  
- **Settings**:
  - Select your purchase request form

### ✅ Step 2: Get Response Details
```powerfx
@triggerOutputs()?['body/resourceData/responseId']
```

### ✅ Step 3: Send Approval Request
- **Connector**: Approvals  
- **Action**: Start and wait for an approval  
- **Details**:
    ```powerfx
    Reason: @{outputs('Get_response_details')?['body/rca14f68076e14783bcab6c0da27aac34']}
    ```

### ✅ Step 4: Condition
```powerfx
@equals(outputs('Start_and_wait_for_an_approval')?['body/outcome'], 'Approve')
```

### ✅ Step 5: Notify in Teams
```
Item Name: @{outputs('Get_response_details')?['body/r7de8f166d17b4edca8de938c3ab221ef']}
Amount: @{outputs('Get_response_details')?['body/r1b9d81fb804c4d51a22d7b2aaeb234bf']}
Comments: @{items('For_each')?['comments']}
```

---

## ✅ Testing
1. Create a Microsoft Form for purchase requests
2. Run the flow and check if approval request reaches Teams
3. Verify that the requester receives the final notification

---

## 📌 Related Links
- **Blog Post**: https://your-blog-url
- **YouTube Video**: https://your-youtube-url

---

## 📜 License
MIT License  
Feel free to use and modify, but credit is appreciated.

---

⭐ **If you find this repository helpful, please give it a Star!**
