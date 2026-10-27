# Global Automotive Production & Sales Analysis
An exploratory data analysis (EDA) project using Python to examine
automotive production, sales, costs, discounts, and profitability across
countries, regions, vehicle brands, models, and distribution channels.

<img width="1004" height="414" alt="image" src="https://github.com/user-attachments/assets/c7d1e30c-312f-4593-9484-aab1125fc372" />


## 🎯 Project Overview:

Automotive businesses need to understand how production costs, selling
prices, order sizes, discounts, and sales channels affect profitability.
This project explores a global automotive dataset covering 2023--2026 to
identify patterns in production-to-sale timelines, regional demand, cost
differences between plants, and profit performance.

The analysis is documented in the Jupyter Notebook:

`Global_Automotive_Production_Sales_Analysis_.ipynb`

## 🎯 Objectives:

-   Analyze global vehicle production and identify international sales
    patterns.
-   Clean and preprocess the source data for analysis.
-   Explore trends and relationships in revenue, production costs,
    discounts, and profit.
-   Compare standard sales and fleet sales.
-   Compare country, region, production plant, brand, model, and
    distribution-channel performance.
-   Present findings through statistical summaries and visualizations.

## 📋 Problem Statements:

The notebook investigates questions including:

-   Which countries and production plants have the lowest and highest
    average production costs?
-   How long does it take vehicles to move from production to sale
    across regions?
-   How do online, dealership, and fleet channels compare in
    profitability?
-   Which vehicle categories have the highest sales volume in each
    region?
-   Which brands and vehicle models perform best on profit-related
    measures?
-   How do production costs compare with net selling prices?
-   Which model/plant combinations have low profit, and how many units
    did they sell?
-   How does fleet sales profitability compare with other channels when
    fleet unit volume is lower?
-   What future sales, inventory, and discount-threshold questions could
    be explored next?

> The notebook raises some forecasting and discount-optimization
> questions, but this README does not claim those tasks have been
> completed unless the notebook contains corresponding analyses.

## 📊 Dataset Information:

-   **Topic:** Global automotive production and sales
-   **Timeline stated in the notebook:** 2023--2026
-   **Source stated in the notebook:** [U.S. Bureau of Transportation
    Statistics (BTS)](https://www.bts.gov/)
-   **CSV loaded by the notebook:**
    [global_automotive_production_sales.csv](https://raw.githubusercontent.com/abiramig1821-pixel/ProductSalesAnalysis-Using-Python/refs/heads/main/global_automotive_production_sales.csv)

The notebook uses fields covering:

-   Transaction ID
-   Production plant and country of origin
-   Production date and sales date
-   Vehicle brand, model, and category
-   Units count
-   Unit production cost, gross price, net price, and discount
    percentage
-   Sales region and distribution channel
-   Total revenue, total production cost, and net profit margin

The raw CSV is loaded directly from the GitHub URL in the notebook, so
an internet connection is required for that cell to run as written.

## 🛠️ Tools and Libraries:

-   **Python** --- analysis and data processing
-   **pandas** --- loading, cleaning, transforming, and aggregating
    tabular data
-   **NumPy** --- numerical operations
-   **Matplotlib** --- charts and plotting
-   **Seaborn** --- statistical visualizations
-   **Jupyter Notebook** --- interactive analysis environment

## 💻 Workflow:

1.  **Load the data** from the CSV source.
2.  **Inspect the dataset** using sample rows, dimensions, data types,
    and descriptive statistics.
3.  **Check data quality** by checking missing values and duplicate
    rows.
4.  **Clean and transform** the data:
    -   Rename `Origin_Country` to `Country`.
    -   Rename `Discount_Applied_Pct` to `Discount`.
    -   Convert `Production_Date` and `Sales_Date` to datetime types.
    -   Derive `Days_to_sell` from the difference between sales and
        production dates.
5.  **Examine outliers and distributions.** The notebook notes that
    unusually large revenue, cost, and profit values may be legitimate
    results of larger order volumes. It therefore segments records
    instead of automatically removing all high values.
6.  **Segment transactions** into:
    -   `standard_sales`: `Units_Count <= 2`
    -   `fleet_sales`: `Units_Count > 2`
7.  **Perform exploratory analysis** with descriptive statistics,
    skewness, kurtosis, and visualizations.
8.  **Export the cleaned data** to
    `Clean - Global Automotive Production Sales Analysis.csv` from the
    notebook.

## 📊 Analysis and Visualizations:

The notebook explores:

-   Revenue, profit, production-cost, and discount distributions for
    standard and fleet sales
-   Total revenue by country
-   Production-to-sale time by sales region
-   Profitability by distribution channel
-   Profit-related performance by vehicle brand
-   Average production cost by plant/country
-   Vehicle-category demand by region
-   Production cost compared with net selling price across vehicle
    models
-   Low-profit vehicle-model and production-plant combinations compared
    with units sold
-   Average profit per unit across distribution channels
-   Profit trends by sales year and month

### 📊 Dashboard 📊:
<img width="778" height="432" alt="Dashboard1" src="https://github.com/user-attachments/assets/994e1d33-49ba-4caf-ad5c-0c21962d4d44" />


## 🏁 Final Insights:

The following are findings written in the notebook and should be
interpreted in the context of its dataset and calculations:

-   **Country revenue:** The USA is reported as the highest-revenue
    country in the country comparison, at approximately USD 136,157.
    Germany is reported as the lowest in that comparison, at
    approximately USD 129,274.
    
-   **Production-to-sale timing:** Regional averages are reported to be
    close to 32 days. Latin America is reported at approximately 32.03
    days and North America at approximately 32.53 days.
    
-   **Distribution channels:** The notebook reports Direct Consumer
    Online as the strongest channel in one overall-profit comparison,
    while its per-unit comparison reports Fleet Enterprise Sales at
    approximately USD 12,815.50 average profit per unit, slightly above
    online and dealership channels.
    
-   **Production costs:** The notebook reports China / Shanghai
    Gigafactory as having the lowest average production cost
    (approximately USD 94,314) and the USA / Detroit Assembly plant as
    having the highest (approximately USD 99,273).
    
-   **Regional demand:** The notebook describes different high-volume
    vehicle categories by region, including EV SUVs in Asia-Pacific,
    Sports EVs in the Middle East, and Compact SUVs in Latin America.
    
-   **Model/plant performance:** The notebook identifies the Ranger
    model at Munich Plant East as a low-profit combination in its
    last-year analysis, with 224 units sold.
    
-   **Outlier handling:** High values in revenue, cost, and profit are
    retained as potentially meaningful business variation, particularly
    where transaction volume differs.

These figures are transcribed from the notebook's interpretations; they
have not been independently validated here. Where different notebook
sections use different profitability measures, distinguish total profit
from average profit per unit.

## Getting Started:

### 1. Requirements:

Install Python and Jupyter Notebook, then install the libraries used by
the notebook:

``` bash
pip install pandas numpy matplotlib seaborn jupyter
```

### 2. Open the notebook:

Place the notebook in your working directory and launch Jupyter:

``` bash
jupyter notebook
```

Open `Global_Automotive_Production_Sales_Analysis_.ipynb` and run the
cells in order.

### 3. Dataset access:

The notebook loads the source CSV directly from GitHub. If you prefer to
work offline, download the CSV from the link in the Dataset section and
update the notebook's `pd.read_csv(...)` path to the local filename.

### 4. Cleaned output:

The notebook includes an export cell that writes:

`Clean - Global Automotive Production Sales Analysis.csv`

The file is created when that cell is run successfully; it may not be
present until then.

## Repository Structure:

A suggested layout for sharing the project:

``` text
.
├── README.md
├── Global_Automotive_Production_Sales_Analysis_.ipynb
└── Clean - Global Automotive Production Sales Analysis.csv  # generated by notebook
```

The CSV shown in the structure is a generated output, not guaranteed to
be included with the notebook.

## Notes and Limitations:

-   The project is primarily exploratory data analysis and
    visualization.
-   Results depend on the dataset and the calculations in the notebook.
-   High revenue or cost values should not automatically be treated as
    data errors; order volume and business context matter.
-   The source attribution and dataset timeline are stated as provided
    in the notebook and are not independently verified in this README.
-   Forecasting future sales/inventory and finding an optimal discount
    threshold are listed as business questions; additional modelling and
    validation would be needed to answer them reliably if they are not
    implemented in the notebook.

## Author:

Abirami Ganesan

Project notebook: **Global Automotive Production Sales Analysis**

For questions or improvements, open an issue or submit a pull request in
the project repository.
