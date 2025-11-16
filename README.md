# 👩‍💻 Created By  
**Monika Sarkar**

---

# 🔄 Salesforce → Business Central Integration With API QA Project

## 📘 Project Overview
This QA project demonstrates a complete **end-to-end API integration** between **Salesforce Accounts** and **Microsoft Business Central Customers**.

![image alt](https://github.com/monikasarkar1809/Salesforce-to-Business-Central-Integration-with-API-/blob/a4a5ed56f2f7203ce7f6b9b7ddf3803e8cf06ad1/Salesforce%20Integration%20With%20Business%20Central.png)


The objective is to validate:
- API connectivity
- Mapping Salesforce Account data to Business Central Customer fields
- Successful creation of customers in Business Central using API
- Error handling (invalid fields, expired token)
- Data consistency between Salesforce and Business Central

This simulates real-world CRM → ERP integration used in finance, billing, and customer onboarding.

---

## 📌 The Project Covers:

### 🔹 Salesforce Side
- Creation of test Accounts  
- Extraction of Account details  
- Data preparation for API integration  

### 🔹 API Testing
- OAuth authentication configuration  
- **GET** request to fetch existing BC customers  
- **POST** request to create a new customer  
- HTTP response code validation  

### 🔹 Business Central Side
- Validation of created customer  
- Field accuracy (Name, Phone, City)  
- Customer numbering (e.g., C00010)  

---

# ⚙️ Key Features Tested

### ✅ GET Integration Testing  
- Successful retrieval of customer list  
- Authentication validation using Bearer tokens  

### ✅ POST Integration Testing  
- Creating a Business Central customer using Salesforce data  
- Verified `201 Created` response  
- Verified fields in BC UI  

### ✅ Field Mapping Validation (SFDC → Business Central)

| Salesforce Field | Business Central Field |
|------------------|-------------------------|
| Account Name | displayName |
| Phone | phoneNumber |
| Billing City | city |
| Billing Street | addressLine1 |
| Currency | currencyCode |


### ✅ Business Central UI Validation  
- New customer appears in Customer List  
- Customer Card fields match Salesforce  
- Customer Number auto-generated (e.g., C00010)

---

# 📊 Business Central Validation Screens

Although Business Central does not contain dashboards for customers like Salesforce, validation focused on:

1️⃣ **Customer List Page**  
2️⃣ **Customer Card Details**  
3️⃣ **API Response Data**  
4️⃣ **Field Mapping Verification**

---

# 📑 Google Sheet – Test Cases  
[https://docs.google.com/spreadsheets/d/1TP_72GkmbMeg0wfoSEikLlZradZKtgqsFyfREIf5q_s/edit?usp=sharing]


# 📸 Screenshots of Integration

### 1. Salesforce Account Used for Integration  
[https://drive.google.com/file/d/1SlOpU1Taur81uIwRbwZvkDEM91nGy5bC/view?usp=sharing]

### 3. Postman – POST Customer (201 Created)  
[https://drive.google.com/file/d/1JwQxs1VSFd5jqhlcAdlFjfFSitRk_P0x/view?usp=sharing]

### 4. Business Central – Customer Created (C00010)  
[https://drive.google.com/file/d/1HLJKZTVG-bFwprtKg-qm0Az0lLoA8ZE8/view?usp=sharing]

### 5. Field Mapping Validation  
[https://drive.google.com/file/d/1gpIblYqZbrMY98BZafYusZnh1-CC4dum/view?usp=sharing]
---

# 🔗 API Endpoints Used

### **GET Customers**
```http
GET https://api.businesscentral.dynamics.com/v2.0/<tenantID>/Production/api/v2.0/companies(<companyID>)/customers
