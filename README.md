# 🚀 IndexedDB Risk Register: The Ultimate Lightweight Risk Management Tool

A highly robust, client-side, browser-based Risk Register application built using pure HTML, CSS, and JavaScript, leveraging the power of **IndexedDB** for fast, reliable, and persistent data storage. Manage your project risks, compliance issues, and operational threats locally without needing a server or complex database setup.

## ✨ Features

| Feature | Description |
| :--- | :--- |
| **IndexedDB Powerhouse** | Utilizes IndexedDB, not unreliable `localStorage`, to handle **thousands of risk records** asynchronously, ensuring the application remains lightning-fast and doesn't freeze the browser. |
| **Zero-Server Architecture** | Runs entirely in your web browser. Just double-click the `index.html` file—no backend, no database setup, no internet required! |
| **Automatic Risk Scoring** | Calculated fields (Initial Score/Rating, Residual Score/Rating) are **greyed out and auto-populated** instantly based on user-inputted Probability and Impact values (1-5), ensuring data integrity and consistency. |
| **Comprehensive Filtering** | Filter risks instantly by **Status, Residual Rating, Risk Owner, and Review Date** (including Overdue/Due Soon categories). |
| **Inline Editing** | Quickly update core fields like **Status, Review Date, and Risk Owner** directly from the main table with a simple double-click. |
| **Robust Data Management** | Seamlessly **Import** and **Export** the entire register via industry-standard **JSON** and **CSV** formats, making data backup and sharing effortless. |
| **Intelligent Date Handling (UK-Ready)** | Includes intelligent date parsing to ensure date fields handle common European formats like `DD/MM/YYYY` during import, while maintaining the correct `YYYY-MM-DD` standard for HTML inputs. |

---

## 💡 Use Case Scenarios

This tool is perfect for any scenario requiring quick, portable, and data-intensive risk tracking:

1.  **Project Management (PMO):** A project manager needs to track and prioritize risks across multiple complex projects, sharing the latest data file with stakeholders weekly.
2.  **Compliance Audits:** A Compliance Officer requires a secure, offline register to log all non-compliance issues and regulatory risks during fieldwork.
3.  **Small Business Operations:** A start-up needs a robust, free tool to log operational threats without the cost or complexity of commercial GRC software.
4.  **Training & Simulation:** Used as a standalone training tool to demonstrate risk calculation, scoring, and mitigation processes.

---

## 🛠️ Step-by-Step Usage Instructions

### 1. How to Get Started (GitHub Instructions)

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/newlatveria/risk-register-idb.git]
    ```
2.  **Navigate to the Directory:**
    ```bash
    cd risk-register-idb
    ```
3.  **Launch the Application:**
    * **The Easiest Way:** Simply **double-click** the `index.html` file in your file explorer.
    * **The Best Way:** For full functionality (especially IndexedDB access across all browsers), open your web server (e.g., VS Code's Live Server extension, or `python -m http.server`) in the directory, and navigate to `http://localhost:xxxx/index.html`.

### 2. How to Add a New Risk

1.  From the main **Risk Register** view, click the **"➕ Add New Risk"** button.
2.  Fill in the required fields (Risk Item, Date Raised).
3.  Enter values (1-5) for **Probability (Initial)** and **Impact (Initial)**. The **Score** and **Rating** fields will **calculate automatically** and are greyed out to prevent manual errors.
4.  Enter the corresponding **Residual** values to see the current risk level.
5.  Click **"Save Risk"**. The new risk is instantly stored in your browser's IndexedDB and you are redirected to the main view.

### 3. Data Import/Export (Backup & Sharing)

The Data Management section allows you to secure your data.

* **Export Data:**
    * Click **"Save as JSON"** or **"Save as CSV"**. The complete dataset is downloaded instantly.
* **Import Data (USE CAUTION):**
    * Click **"Load Data"** and select a previously exported `.json` or `.csv` file.
    * **⚠️ WARNING:** This action will **completely replace all existing risks** in your current IndexedDB database. Use this feature only when restoring from backup or replacing the entire register.

---

## ❓ Frequently Asked Questions (FAQ)

### Q1: Where is my data stored? Is it safe?

Your data is stored securely in your browser's **IndexedDB**, a persistent client-side storage mechanism.
* **Safety:** The data never leaves your computer or browser unless you explicitly export it. It is entirely private and offline.
* **Persistence:** The data will remain even if you close the browser, clear the cache, or shut down your computer.

### Q2: Why are the Score and Rating fields greyed out?

These fields are **calculated fields**. They are read-only (`readonly`) because they are instantly computed based on the **Probability** and **Impact** inputs (Score = Probability × Impact). This prevents manual errors and ensures consistent risk metrics across the register, as intended by risk methodology.

### Q3: What happens if I try to import a CSV with duplicate Risk Numbers?

The application is smart! During import, it checks the incoming data against the existing database. If a risk number is **missing, invalid, or already exists**, the system will **automatically assign the next available sequential unique risk number** to the incoming record to prevent data loss or database key conflicts.

### Q4: I double-clicked the HTML, but data won't save/load reliably.

In some browsers (like Chrome), running the HTML file directly (`file://...`) restricts access to advanced browser APIs like IndexedDB for security reasons.
**The Fix:** Use a simple local server (e.g., VS Code's Live Server or the Python simple HTTP server) to run the file from `http://localhost:xxxx/`. This resolves all security restrictions and guarantees proper database operation.
