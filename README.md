This is a **great foundation** for your Splunk log analysis project! Let's clean it up, fill in missing SPL queries, and format it as a **ready-to-submit project summary** you can use on your CV, GitHub, or portfolio.

---

## 📊 Splunk Log Analysis – Authentication Logs

This project demonstrates how to analyze authentication logs using **Splunk** for **threat detection** and **incident investigation**. The dataset was structured in **CSV format**, simulating real-world login attempts with both successful and failed logins.

---

### 🔍 Objective

To identify:

* **Brute-force login patterns**
* **Targeted usernames**
* **Suspicious IP addresses**
* **Peak login hours**

Using **Splunk SPL (Search Processing Language)**.

---

### 📁 Dataset Info

* **File**: `auth_log_sample.csv`
* **Sourcetype**: `csv_auth_logs`
* **Index**: `main`

---

### 🔧 Tools Used

* **Splunk (free version)**
* **Search Processing Language (SPL)**
* **Structured CSV Authentication Logs**

---

### 🔎 Use Case Scenarios & Queries

| 🧩 Question                                        | 🔍 SPL Query                                                     |                                 |                     |                |
| -------------------------------------------------- | ---------------------------------------------------------------- | ------------------------------- | ------------------- | -------------- |
| **1. Total login events**                          | \`index=main sourcetype=csv\_auth\_logs                          | stats count as total\_logins\`  |                     |                |
| **2. Top 5 IPs by login attempts**                 | \`index=main sourcetype=csv\_auth\_logs                          | stats count by source\_ip       | sort - count        | head 5\`       |
| **3. Most targeted usernames (failed attempts)**   | \`index=main sourcetype=csv\_auth\_logs status="Failed password" | stats count by user             | sort - count        | head 5\`       |
| **4. Peak login hour**                             | \`index=main sourcetype=csv\_auth\_logs                          | eval hour=strftime(\_time,"%H") | stats count by hour | sort hour\`    |
| **5. Brute-force suspects (IPs with >5 failures)** | \`index=main sourcetype=csv\_auth\_logs status="Failed password" | stats count by source\_ip       | where count>5       | sort - count\` |

---

### 📸 Screenshots to Include

* ✅ **Dataset upload confirmation**
* ✅ **Sourcetype & index setup**
* ✅ **Query results (table or chart):**

  * Top IPs
  * Most targeted users
  * Brute-force IPs
  * Login activity per hour
* ✅ **Graphical visualizations (bar/pie charts)**

---

### 🧠 Lessons Learned

* Gained **hands-on experience** with SPL operators: `stats`, `eval`, `where`, `sort`, `head`
* Practiced **real-world threat detection** scenarios (e.g., brute-force analysis)
* Understood **how a SOC analyst uses Splunk** for daily log monitoring
* Improved ability to interpret **log patterns and anomalies**

---
