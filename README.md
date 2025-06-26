📊 Splunk Log Analysis – Authentication Logs
This project demonstrates how to analyze authentication logs using Splunk for threat detection and incident investigation. The dataset was structured in CSV format and simulates real-world login attempts with both successful and failed logins.

🔍 Objective
To identify brute-force login patterns, targeted usernames, suspicious IPs, and peak login hours using Splunk's SPL queries.

📁 Dataset
File: auth_log_sample.csv
Sourcetype: csv_auth_logs
Index: main
🔧 Tools Used
Splunk (free version)
SPL (Search Processing Language)
Sample authentication log in CSV
🔎 Use Cases
Question	SPL Query
🔹 Total login events	`index=main sourcetype=csv
🔹 Top 5 IPs by login attempts	`index=main sourcetype=csv
🔹 Most targeted usernames	`index=main sourcetype=csv status="Failed password"
🔹 Peak login hour	`index=main sourcetype=csv
🔹 Brute-force suspects (IPs with >5 failures)	`index=main sourcetype=csv status="Failed password"
📸 Screenshots

Include screenshots of:

Uploaded dataset
Query outputs
Graphs or tables showing IPs, users, login patterns
🧠 Lessons Learned

Learned how to use SPL effectively (stats, eval, where, sort, head)
Detected suspicious activity patterns in structured logs
Practiced core skills of log analysis used in real SOC environments
