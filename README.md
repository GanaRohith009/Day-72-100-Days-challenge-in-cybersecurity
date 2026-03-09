# Day-72-100-Days-challenge-in-cybersecurity
## 🗓️ Day 72: Brute Force Attack Analysis (DVWA - Medium Level)

### 🎯 Objective
To perform a successful brute force attack on a medium-security web application and understand how defensive mechanisms like input sanitization and rate limiting affect attack velocity.

### 🛠️ Tools Used
* **Proxy:** Burp Suite Professional (Interception)
* **Automation:** Burp Intruder
* **Environment:** DVWA (Medium Security)

### 🔍 Methodology
1.  **Interception:** Captured the login POST request using Burp Proxy to identify the `username` and `password` parameters.
2.  **Configuration:** Transferred the request to **Intruder**, set payload positions on the credentials, and selected the **Cluster Bomb** attack type.
3.  **The "Medium" Hurdle:** * Observed a **2-second server-side delay** on every failed attempt.
    * Calculated the impact: An attack on 1,000 entries increased from ~10 seconds to **~33.3 minutes**.
4.  **Analysis:** Monitored the `Length` column in the Results tab. Identified the successful credential pair by locating the **Response Length Outlier** (the only response size that differed from the failed attempts).

### 💡 Key Learnings
* **Input Sanitization:** Effectively prevents "breaking out" of SQL queries by treating inputs as literal strings.
* **Throttling:** Adding time delays is a powerful, low-cost psychological and technical deterrent against automated bots.
* **Side-Channel Attacks:** Even when a server doesn't explicitly say "Success," differences in response size or time can leak the truth.

---
