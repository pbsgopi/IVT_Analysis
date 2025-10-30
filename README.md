# 🧠 IVT Traffic Pattern Analysis

### 📄 Project Overview
This project analyzes ad traffic data from six mobile applications to identify and explain patterns associated with **Invalid Traffic (IVT)** — such as bot-generated or spoofed ad requests.  
The dataset includes hourly metrics such as unique devices, IPs, user-agents, requests, impressions, and calculated ratios.  
Three apps were flagged as IVT at different times, while the remaining three represent valid, non-IVT traffic.

---

### 🎯 Objective
To determine **why some apps were marked as IVT earlier or later** by:
- Comparing traffic metrics across apps
- Identifying anomalies in request and impression behavior
- Detecting unusual device-to-user-agent ratios indicating possible spoofing

---

### ⚙️ Steps Performed

#### 1️⃣ Data Loading & Preparation
- Combined six Excel sheets (`Valid 1–3`, `Invalid 1–3`) into one unified dataset  
- Added metadata for grouping apps as **Valid** or **Invalid**

#### 2️⃣ Exploratory Data Analysis (EDA)
- Examined key metrics such as `requests_per_idfa`, `idfa_ua_ratio`, and `IVT`
- Visualized hourly trends and compared Valid vs Invalid app behavior
- Analyzed consistency between requests, impressions, and device counts

#### 3️⃣ Invalid Traffic Pattern Detection
- Implemented a **dynamic spike detection algorithm** to find the first significant IVT increase for each app  
- Compared timing and severity of IVT spikes between Valid and Invalid apps

#### 4️⃣ Reporting & Export
Generated the following reports:
- 📊 `IVT_App_Summary.xlsx` — Mean metric comparisons by app and traffic group  
- ⚠️ `IVT_App_Summary_with_Spikes.xlsx` — Adds first IVT spike timestamp and magnitude  

---

### 📈 Key Insights
- **Invalid apps** showed **early and large IVT spikes** (≥0.5) and abnormally high `idfa_ua_ratio` values (hundreds of devices per UA).  
- **Valid apps** maintained low IVT values and stable metrics over time.  
- Most IVT detections aligned with **sudden increases in UA ratios**, suggesting bot or spoofed traffic surges.

---

### 🧰 Tech Stack
- **Python 3**
- **Pandas**, **NumPy**
- **Matplotlib**, **Seaborn**
- **Jupyter Notebook** for visualization
- **Excel (.xlsx)** for export and reporting

---

### 📦 Deliverables
| File | Description |
|------|--------------|
| `IVT_Analysis.ipynb` | Main analysis notebook |
| `IVT_App_Summary.xlsx` | Summary of mean metrics per app |
| `IVT_App_Summary_with_Spikes.xlsx` | Includes IVT spike detection results |

---

### 🧠 Example Visualizations
- Boxplots comparing `idfa_ua_ratio` between valid and invalid apps  
- Time series of IVT scores per app  

---

### 👨‍💻 Author
Developed by **Bhaskar Sri Gopi Pedamallu**  
📧 Contact: **gopipedamallu@gmail.com**

---

### 🪄 How to Reproduce
1. Clone this repository  
   ```bash
   git clone https://github.com/pbsgopi/IVT_Analysis.git
   cd IVT_Analysis
