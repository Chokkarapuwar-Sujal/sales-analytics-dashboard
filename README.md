# Sales Data Analytics Dashboard

![Python](https://img.shields.io/badge/Python-3.13-blue)
![Framework](https://img.shields.io/badge/Framework-Streamlit-red)
![Data](https://img.shields.io/badge/Data-Pandas-lightblue)
![Charts](https://img.shields.io/badge/Charts-Plotly-1f77b4)
![ML](https://img.shields.io/badge/ML-Scikit--learn-orange)
![Boosting](https://img.shields.io/badge/Boosting-XGBoost-green)

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://your-dashboard-name.streamlit.app)

A production-style Streamlit dashboard for sales analytics, business intelligence, ML-powered forecasting, and automated insights. The app ships with an Indian e-commerce sample dataset and also supports compatible custom CSV files.

---

## Features

### Core Analytics
- KPI cards: Total Sales, Total Profit, Orders, Average Order Value
- Sales trend with daily, weekly, monthly granularity
- Secondary metrics: Sales Loss, Average Sales, Profit Rate, Loss Rate

### Products Tab
- Top products by `quantity * profit`
- Highest loss products by `quantity * abs(loss)` using raw profit values
- Category sales distribution
- Product demand scatter
- Custom chart builder with 12 chart types (bar, horizontal bar, pie, donut, treemap, funnel, scatter, bubble, line, area, heatmap, box)

### Regions Tab
- Regional sales distribution with profit-margin coloring
- Region-wise profit chart
- Region x category heatmap
- Automatic best and weakest region callout

### Customers Tab
- Top customers by revenue
- Order frequency histogram
- K-means segmentation: High Value, Medium Value, Low Value
- Segment chart, scatter, and summary table

### Forecast Tab
- KPI cards: Total Revenue, Projected Revenue, Best Method, Prediction Accuracy
- Model comparison charts (accuracy and average prediction error)
- Historical vs predicted sales chart
- Forecast table with actual and predicted sales side by side

### Insights Tab
Automated plain-language insights from the filtered dataset include:
- Top revenue category and share
- Highest profit-margin region
- Repeat buyer count and order frequency
- Best-selling product contribution
- Peak vs slowest month
- Year-over-year revenue trend
- Overall margin with strongest/weakest category

### Export Features
- CSV and Excel export in each section
- Exports respect active filters (date, region, category, product)

---

## Forecasting Models

The app compares three forecasting models with lag and seasonality features:

| Model | Details |
|---|---|
| Linear Regression | Baseline trend model |
| Random Forest | 300 trees, max depth 6 |
| XGBoost | 300 estimators, learning rate 0.05 |

Feature set includes time index, year, quarter, month, sinusoidal seasonality, quantity, lag-1, lag-2, and 3-month rolling average.

---

## Tech Stack

| Library | Purpose |
|---|---|
| Streamlit | Dashboard UI |
| Pandas | Data wrangling and aggregation |
| Plotly | Interactive visualizations |
| Scikit-learn | K-means, Linear Regression, Random Forest |
| XGBoost | Gradient-boosted forecasting |
| NumPy | Numerical feature engineering |
| openpyxl | Excel exports |

---

## Project Structure

```text
app.py
src/
  analytics.py
  forecasting.py
  sales.csv
requirements.txt
```

---

## Dataset

Default dataset: `src/sales.csv`

- Rows: 182
- Date range: Jan 2024 to Dec 2024
- Cities: Mumbai, Bangalore, Delhi, Chennai, Hyderabad, Pune, Ahmedabad, Kolkata, Jaipur
- Categories: Smartphones, Laptops, Televisions, Home Appliances, Audio, Gaming, Cameras, Refrigerators

---

## Required CSV Columns

These columns are currently required by the app loader:

| Column | Type | Notes |
|---|---|---|
| `order_id` | string | Unique order identifier |
| `order_date` | date | Parsed to datetime |
| `region` | string | City or territory |
| `category` | string | Product category |
| `product` | string | Product name |
| `sales` | float | Revenue per order |
| `profit` | float | Can be negative |
| `quantity` | int | Units sold |
| `customer_name` | string | Customer identifier |

---

## Quick Start

```bash
git clone https://github.com/<your-username>/salesdashboard.git
cd salesdashboard
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate
pip install -r requirements.txt
streamlit run app.py
```

---

## Usage

1. Open the sidebar filters (date, region, category, product).
2. Set forecast horizon (3 to 12 months).
3. Explore tabs for products, regions, customers, forecast, and insights.
4. Export filtered outputs as CSV or Excel.

---

## Real-World Use Cases

- Retail and e-commerce sales tracking
- Demand forecasting and inventory planning
- Customer segmentation for campaigns
- Regional performance monitoring
- Executive BI reporting


