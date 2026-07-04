# Quick-Commerce Sales & Logistics Analysis 📊🚚

Welcome to the **Quick-Commerce Sales & Logistics Analysis** repository. This project focuses on analyzing, cleaning, and extracting actionable commercial and logistical insights from a massive dataset (1,000,000 records) of a Quick-Commerce (Q-Commerce) delivery platform.

The analysis is implemented using **Python**, leveraging key data science libraries such as **Pandas**, **NumPy**, **Matplotlib**, **Seaborn**, and **Plotly** to evaluate delivery operations, customer behavior, and financial performance across major Indian cities and top industry platforms.

---

## 🚀 Key Objectives & Strategy

Instead of just checking technical tasks, this project is built around a **business-driven narrative** to deliver tangible strategic value:
- **Operational Optimization:** Enhancing logistics KPIs like *On-Time Delivery (OTD)* rates, assessing delivery times relative to distance, and analyzing delivery partner performance.
- **Customer Experience & Retention:** Identifying factors affecting customer satisfaction through localized analysis of ratings, item counts, and demographics.
- **Revenue & Marketing Efficiency:** Evaluating transaction/invoice volumes based on financial codes, order values, discount impacts, and payment gateway distributions.

---

## 🛠️ Tech Stack & Environment

This project utilizes a robust local development environment tailored for professional data pipelines:
- **Language:** Python 3.x
- **Development Environment:** Specialized IDE / Jupyter Notebook
- **Data Manipulation:** `pandas`, `numpy`
- **Statistical Operations:** `scipy`
- **Data Visualization:** `matplotlib`, `seaborn`, `plotly.express`
- **Environment & Infrastructure:** Configured locally with Docker containerization and version-controlled via Git.

---

## 📊 Dataset Overview & Features

The raw data (`quick_commerce_data_raw.csv`) contains **1,000,000 transaction records** with 13 crucial columns capturing both business metrics and operations:

| Column Name | Data Type | Description / Context |
| :--- | :---: | :--- |
| `Order_ID` | `int64` | Unique identifier for each customer transaction. |
| `Company` | `object` | The Q-Commerce platform provider (e.g., Swiggy Instamart, Blinkit, Zepto, Dunzo, Flipkart Minutes, Amazon Now, Big Basket). |
| `City` | `object` | The city where the order was placed (e.g., Noida, Mumbai, Delhi, Kolkata, Chennai, Bengaluru, Pune, Hyderabad, Amritsar). |
| `Customer_Age` | `int64` | Age of the registered customer (ranging from 18 to 59 years). |
| `Order_Value` | `float64` | The total monetary value of the invoice transaction. |
| `Delivery_Time_Min` | `float64` | Total time taken for delivery fulfillment (in minutes). |
| `Distance_Km` | `float64` | Travel distance between the dark store/hub and customer location. |
| `Items_Count` | `float64` | Total number of items packed within the order transaction. |
| `Product_Category` | `object` | Category of the ordered goods (e.g., Dairy, Snacks, Personal Care, Beverages, Household, Groceries, Fruits & Vegetables). |
| `Payment_Method` | `object` | Gateway used (e.g., Wallet, Cash on Delivery, Credit Card, UPI, Debit Card). |
| `Customer_Rating` | `float64` | Satisfaction score given by the customer (Scale: 1.0 - 5.0). |
| `Discount_Applied` | `int64` | Binary flag (`1` or `0`) indicating whether a promotion code was used. |
| `Delivery_Partner_Rating`| `float64` | Evaluation rating assigned to the dispatch courier rider. |

### Data Model Clarification 📝
* **Contextual Note:** Through manual data profiling, column codes and invoice identifiers represent independent, sequential transactional metadata rather than fixed product inventory SKU codes.

---

## 🧹 Professional Data Cleaning Pipeline

A rigorous data engineering and cleaning workflow was executed to handle missing data and ensure mathematical integrity across all 1,000,000 rows:

1. **Initial Structural Inspection:**
   Using `df.info()` and `df.describe()`, structural distribution anomalies, standard deviations, and missing fields were identified.

2. **Categorical Handling (Listwise Deletion):**
   - **Column:** `City` (52,000 missing values detected).
   - **Action:** Rows with missing city coordinates were completely removed using listwise dropping since geographic distribution is crucial for regional logistics modeling.
   - **Result:** Dataset refined to **948,000 records**.

3. **Mode Imputation:**
   - **Column:** `Items_Count` (35,000 missing values).
   - **Action:** Filled missing entries with the dataset's standard categorical Mode (the most frequent item count).

4. **Advanced Group-wise Strategic Imputation:**
   - **Columns:** `Customer_Rating` (47,000 missing) and `Delivery_Partner_Rating` (104,137 missing).
   - **Action:** Imputed missing values dynamically using the **Group-wise Mean** calculated per `Company`. This preserves the distinctive service levels and ratings profile unique to each individual brand platform instead of applying a generic global mean.
   - **Secondary Fill:** Any remaining boundary null values were securely patched with the general operational mean.

---

## 📈 Strategic Insights & Analysis Roadmap

The clean data is ready for exploratory data analysis (EDA) and business intelligence dashboard design:

- **Logistics Breakdown:** Correlating `Distance_Km` against `Delivery_Time_Min` to benchmark fleet velocity and isolate bottlenecks.
- **Demographic Penetration:** Grouping `Customer_Age` brackets against `Product_Category` preferences to refine targeted automated workflows.
- **Financial & Promotions Strategy:** Analyzing how `Discount_Applied` influences the average `Order_Value` and choice of `Payment_Method`.

---

   git clone [https://github.com/your-username/quick-commerce-analysis.git](https://github.com/your-username/quick-commerce-analysis.git)
   cd quick-commerce-analysis
