# 🛡️ Risk Register IDB
### The Professional, Offline-First Risk Management Suite

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Technology](https://img.shields.io/badge/tech-HTML5%20%7C%20JS%20%7C%20IndexedDB-orange)

**Risk Register IDB** is a powerful, browser-based application designed to replace clunky spreadsheets with a dynamic, interactive risk management interface. Built on **Vanilla JavaScript** and **IndexedDB**, it offers enterprise-grade features—like dependency mapping, rich text editing, and automated scoring—without requiring a backend server, database installation, or internet connection.

**Your data lives in your browser. It never leaves your device.**

---

## 🚀 Key Features

### 🧠 Intelligent Data Core
* **IndexedDB Backend:** Uses the browser's native database to store thousands of records asynchronously. Fast, persistent, and capable of handling much larger datasets than LocalStorage.
* **Auto-Scoring:** Automatically calculates **Initial** and **Residual** risk scores (Probability × Impact) and assigns RAG (Red/Amber/Green) ratings instantly.

### 🕸️ Advanced Visualization
* **Dependency Mapping:** Visualize the "Butterfly Effect" of your risks. The **Risk Map** module draws a dynamic network graph showing how one risk impacts another, helping you identify central points of failure.
* **Cluster Analysis:** Visual nodes are sized by criticality and colored by rating, allowing for instant visual triage.

### ✍️ Rich Editing & Reporting
* **Rich Text Support:** Integrated **Quill.js** editors allow for formatted text (bullet points, bolding, colors) in descriptions, mitigations, and history logs.
* **Inline Editing:** Double-click any key field in the main dashboard to edit it instantly without opening the full form.
* **Professional Reporting:** Includes a dedicated **Report View** (`all_risks.html`) optimized for printing to PDF, complete with sorting options (Criticality, Date, Owner).

### 🔄 Robust Data Management
* **Universal Import/Export:** Seamlessly move data in and out using standard **JSON** or legacy **CSV** formats.
* **Smart Import Logic:** The importer automatically detects duplicate IDs, standardizes UK/US date formats, and merges legacy data structures.

---

## 📖 Usage Guide

### 1. Installation & Setup
Because this application uses advanced browser features (CORS for default files, ES6 Modules), it requires a local web context.

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/newlatveria/risk-register-idb.git](https://github.com/newlatveria/risk-register-idb.git)
    ```
2.  **Run Locally:**
    * **Using Python (Recommended):**
        ```bash
        cd risk-register-idb
        python -m http.server 8000
        ```
    * **Using IIS / Web Server:** Point your web root to the project folder.
3.  **Access:** Open your browser and navigate to `http://localhost:8000`.

### 2. Managing Risks
* **Dashboard:** The main view lists all risks. Use the dropdowns at the top to filter by **Status**, **Rating**, **Owner**, or **Review Urgency** (e.g., "Due in 7 Days").
* **Adding/Editing:** Click "Add New Risk" to open the detailed form.
    * *Note:* Risk Scores are read-only; they calculate automatically when you adjust Probability/Impact sliders.
* **Linking Risks:** In the edit form, find the **"Linked Risks"** field. Enter the ID numbers of related risks (e.g., `1001, 1005`). This powers the Network Map.

### 3. The Network Map
Click the **🕸️ View Risk Map** button on the dashboard.
* **Nodes:** Represent individual risks.
* **Arrows:** Represent dependencies (Cause $\to$ Effect).
* **Colors:** Red (Critical), Orange (High), Yellow (Medium), Blue/Green (Low).
* **Interaction:** Drag nodes to rearrange the web. Double-click a node to edit that specific risk.

---

## 💡 Use Case Scenarios

### Scenario A: The Project Manager 🏗️
* **Challenge:** You are managing a construction project with tight deadlines. You need to track safety hazards and supply chain delays.
* **Solution:** You load the tool on your laptop. You use the **Review Date Filter** to see exactly which risks need a safety inspection this week. You use the **Risk Map** to show stakeholders how a "Supplier Delay" (Risk 1005) directly causes a "Safety Certification Failure" (Risk 1020).

### Scenario B: The CISO (Security Officer) 🔐
* **Challenge:** You need to maintain a confidential risk register for ISO 27001 compliance, but you cannot upload sensitive vulnerability data to a public cloud SaaS.
* **Solution:** You use Risk Register IDB. The data resides **encrypted in your local browser profile**. You use the **Rich Text** fields to paste detailed snippets of code vulnerabilities and mitigation plans. You export a **JSON backup** weekly to a secure, encrypted local drive.

### Scenario C: The Compliance Auditor 📋
* **Challenge:** You are auditing a department and need to see a history of their risk mitigation.
* **Solution:** You ask the department lead to click **"View Full Report"**. You sort by **"Highest Initial Risk"** to see what their biggest inherent threats are. You print the view to PDF to include as an appendix in your audit findings.

---

## 📂 Project Structure

| File | Function |
| :--- | :--- |
| `index.html` | **The Dashboard.** Main table view, filtering logic, and IndexedDB CRUD wrappers. |
| `risk_form.html` | **The Editor.** Detailed data entry with Quill.js integration and auto-calculation logic. |
| `risk_map.html` | **The Visualizer.** Vis.js network graph implementation for dependency analysis. |
| `all_risks.html` | **The Reporter.** Read-only, printer-friendly view for board reporting. |
| `data_management.html` | **The Admin.** Tools to nuke the database or perform hard resets. |
| `/data/default_risks.json` | A starter dataset for testing or initializing new projects. |

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.