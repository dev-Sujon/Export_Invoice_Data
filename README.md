# 📊 Export Invoice Summary & Pending Report

## 📌 Overview

This project generates a comprehensive **Export Invoice Summary Report** along with a **Pending Report** from raw export data. It processes, cleans, and transforms datasets to provide actionable insights into invoicing, payments, and outstanding balances.

The system is designed to automate reporting workflows typically used in export-oriented businesses (e.g., garments, manufacturing, trading).

---

## ⚙️ Features

* ✅ Data cleaning and preprocessing
* ✅ Automatic date parsing and formatting
* ✅ Handling missing and inconsistent data
* ✅ Structured output for reporting (Excel/DataFrame)
* ✅ Debugging support for common issues (e.g., `NaT` in dates)
* ✅ Invoice summary generation
* ✅ Pending payment tracking

---

## 📂 Dataset Structure

The input dataset includes columns such as:

* `Invoice_No`
* `Invoice_Date`
* `Invoice_Value`
* `Invoice_Qty`
* `EXP_No`
* `EXP_Date`
* `Buyer`
* `Destination`
* `Carton_Qty`
* `Discount`
* `Commission`
* `Ex_Factory_Date`
* `Payment_Due_Date`
* `Realize_Date`

---

## 🔄 Processing Workflow

### 1. Data Loading

* Read Excel/CSV files into a Pandas DataFrame

### 2. Data Cleaning

* Handle null values (`NaN`, `"null"`, `"-"`)
* Standardize column names
* Remove invalid rows

### 3. Data Type Conversion

* Convert date columns using `pd.to_datetime()`
* Convert numeric columns properly (int/float)

### 4. Report Generation

#### 📘 Invoice Summary Report

* Total invoices
* Total quantity
* Total value
* Buyer-wise summary

#### ⏳ Pending Report

* Identify unpaid invoices
* Calculate due amounts
* Track payment delays

---

## 🧠 Common Issues & Fixes

### ❗ Invoice Date Showing `NaT`

**Possible Causes:**

* Incorrect date format
* Mixed data types
* Hidden characters or spaces

**Solution:**

```python
df['Invoice_Date'] = pd.to_datetime(df['Invoice_Date'], errors='coerce')
```

Additionally:

```python
df['Invoice_Date'] = df['Invoice_Date'].astype(str).str.strip()
```

---

## 🛠️ Technologies Used

* Python 🐍
* Pandas
* NumPy
* OpenPyXL / Excel Writer

---

## 📦 Output

The script generates:

* 📄 **Invoice Summary Report**
* 📄 **Pending Payment Report**

Outputs can be exported to:

* Excel (`.xlsx`)
* CSV (`.csv`)

---

## 🚀 How to Run

1. Install dependencies:

```bash
pip install pandas numpy openpyxl
```

2. Run the script:

```bash
python report_generator.py
```

3. Check output files in the specified directory.

---

## 📈 Use Cases

* Export business reporting
* Accounts & finance tracking
* Buyer payment monitoring
* Operational dashboards

---

## 📬 Contribution

Feel free to contribute by:

* Improving data validation
* Adding visualization (charts/dashboard)
* Optimizing performance

---

## 🧾 License

This project is open-source and available for modification and use.

---
