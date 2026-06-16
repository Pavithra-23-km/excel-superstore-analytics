# excel-superstore-analytics
A localized retail data analytics project optimizing delivery timelines and regional profit margins using advanced excel function

 **📊 Project Overview**
A comprehensive data analysis project focused on cleaning, structuring, and optimizing global retail data. This project transforms raw transactional data into executive-level insights, helping corporate leaders track delivery speeds, protect regional profit margins, and monitor product sales trends.

---

### 🛠️ Section 1: Master Table Architecture

| Column Name | Technical Formula / Function Used | Business Insight & Purpose |
| :--- | :--- | :--- |
| **Returned Status** | `=IFERROR(VLOOKUP(B2, Returns!A:B, 2, FALSE), "No")` | Maps matching order IDs to flag returned products, keeping inventory counts accurate. |
| **Regional Manager** | =INDEX('People Sheet'!$A$4:$B$8,MATCH([@Region],'People Sheet'!$B$4:$B$8,0),1) | Pulls the exact manager in charge of each region to track employee performance. |
| **Target Met** | `=IF([@Profit]/[@Sales]>=0.15,"Target Achieved","Below Target")` | Instantly flags shipping delays by checking if delivery took more than 3 days. |
| **Discount Threshold**| `IF([@Discount]>0.2,"High Discount","Standard/No Discount") | Flags orders with dangerous discounts over 20% that threaten our profit margins. |
| **Discount Category** | Nesting `IF` or `IFS` (e.g., Low, Medium, High) | Categorizes discount levels to see which discount ranges are used most often. |
| **Profit Status** | `=IF(Profit>0, "Profitable", "Loss")` | Instantly labels every transaction as a financial gain or loss for quick sorting. |
| **Margin Alert** | `=IF(Margin<0.1, "Low Margin", "Healthy")` | Flags low-profit orders that are costing the company money to process. |
| **Clean Customer Name**| `=PROPER(TRIM(CustomerName))` | Cleans up human typing errors by removing extra spaces and capitalizing names perfectly. |

---

### 📋 Section 2: Sheet-by-Sheet Architecture

#### 1. Executive Dashboard Sheet
* **Features Built:** Average Logistic Processing Speed by Ship Mode and Discount Level vs. Profit Summary.
* **Business Purpose:** Helps corporate leaders quickly catch shipping delays and see if big discounts are destroying the company's profit.

#### 2. Profit Sheet
* **Features Built:** Regional Profitability Analysis by product categories using custom Stacked Charts.
* **Business Purpose:** Lets regional directors see exactly which product lines are making money and which specific regions are losing money.

#### 3. Sales Sheet
* **Features Built:** Sales Performance Analysis by Segment and Sub-Category.
* **Business Purpose:** Helps marketing and inventory teams see which specific product models are driving the highest customer demand.

#### 4. Sales Year View Sheet
* **Features Built:** Year-over-Year Sales Performance Dashboard using a grouped PivotTable styled in a professional blue and white theme.
* **Business Purpose:** Gives company leaders a high-level historical timeline of long-term business growth trends.

#### 5. Master Orders Sheet
* **Features Built:** Transactional database cleaned and optimized with advanced calculated columns.
* **Business Purpose:** Serves as the accurate, centralized data foundation feeding clean information into all sheets.

---

### 🔒 Project Security & Governance
* **Formula Protection:** All advanced calculation columns have been **Locked and Password Protected**.
* **Purpose:** This ensures the structural integrity of the spreadsheet logic remains intact, preventing accidental edits while allowing users full read-access to the dashboards.
