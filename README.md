# 📝 Serverless School Inquiry & Analytics System

A lightweight, production-ready **Admissions Inquiry System** built with Python and Streamlit. This project solves a common development hurdle: **storing live user data securely without spinning up or paying for a traditional database infrastructure.**

Instead of SQL, this system implements a serverless architecture leveraging the **GitHub REST API** to securely stream, decode, and append user records directly into a version-controlled CSV data lake.

---

## 🚀 Live Applications

* **📋 Public Inquiry Portal:** [shriswarup-dav.streamlit.app](https://shriswarup-dav.streamlit.app/)
* **📊 Admin Management Panel:** [shri47panel.streamlit.app](https://shri47panel.streamlit.app/)

### 🔑 Portfolio Demo Access
Recruiters and reviewers can access the live analytics administration deck using these credentials:
* **Username:** `shriswarup`
* **Password:** `admin@123`
*(Note: Credentials are case-sensitive)*

---

## 🛠️ Deep Tech Stack & Architecture

This application architecture focuses on high resource efficiency and zero operational costs:

* **Streamlit:** Powers both decoupled front-end micro-apps (the public-facing data intake form and the protected business intelligence panel).
* **GitHub REST API:** Replaces traditional database read/write queries. Uses secure API hooks to fetch files, commit changes, and update files over HTTPS.
* **Pandas & StringIO:** Manages real-time data frame mutations, data cleaning, and programmatic input parsing in memory.
* **Plotly Express:** Generates dynamic, interactive statistical charts within the administration dashboard to display demographic trends.
* **Base64 Encoding:** Handles binary-to-text translation required by the GitHub API endpoints to patch raw CSV changes securely.

---

## ✨ Engineering Features

### 🔒 Secure Token & Credential Management
* Fully integrated with Streamlit Secret Management (`st.secrets`) to isolate personal developer tokens.
* Protected admin panel utilizing string-matching conditional authentication gateways.

### ⚡ Data Integrity & Input Validation
* **Duplicate Detection:** Scans existing records programmatically (`.any()` indexing match over Name, Class, and Section) to prevent duplicate double-submits.
* **Format Enforcers:** Active logical guardrails preventing blank names, enforcing specific 10-digit numeric mobile boundaries, and verifying clear email syntax before opening an API connection.

---

## 💻 Local Workspace Configuration

Follow these quick instructions to spin up this project on your local machine:

### 1. Repository Setup
```bash
git clone https://github.com
cd school-inquiry-datastore
```

### 2. Environment Assembly
```bash
pip install -r requirements.txt
```

### 3. Inject Local Environment Secrets
Create a `.streamlit` folder in your project's root directory containing a `secrets.toml` file:
```toml
# .streamlit/secrets.toml
GITHUB_TOKEN = "your_personal_access_token_here"
```

### 4. Initialize Local App Port
```bash
streamlit run DAV_Reg.py
```

---
Developed by [Shriswarup](https://github.com/shriswarup-m)
