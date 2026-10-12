# Customer Segmentation using K-Means

Grouping 99,457 retail customers into 5 segments using age, quantity and total spend, to find who the big spenders are and how to target each group.

## About the Project

Retail businesses have many customers, but they do not all buy in the same way. In this project I used **K-Means clustering** to split customers into groups, so a business can understand each group and plan offers for it.

The full work is in the notebook: [`customer-segmentation-kmeans.ipynb`](customer-segmentation-kmeans.ipynb)

## Dataset

- **Source:** [Sales and Customer data on Kaggle](PASTE_KAGGLE_LINK_HERE)
- **Size:** 99,457 customers (each customer has one purchase)
- **Files:** `sales_data.csv` and `customer_data.csv`, joined on `customer_id`

| Column | Description |
|---|---|
| `invoice_no` | Invoice number |
| `customer_id` | Customer ID |
| `category` | Product category (Clothing, Shoes, Books, etc.) |
| `quantity` | Number of items bought |
| `price` | Price per item |
| `invoice_date` | Date of purchase |
| `shopping_mall` | Shopping mall |
| `gender` | Customer gender |
| `age` | Customer age |
| `payment_method` | Cash, Credit Card or Debit Card |

## What I Did

1. **Merged** the sales and customer files on `customer_id`.
2. **Created** a new column `total = quantity x price`.
3. **Cleaned the data:** found 119 missing ages and filled them with the median. Converted `invoice_date` to a date format.
4. **Explored the data (EDA):** checked age, total spend and category. Total spend is right-skewed, as a few customers spend much more than the rest.
5. **Scaled** the features (`age`, `quantity`, `total`) using `StandardScaler`, so large values do not dominate.
6. **Chose K = 5** using the elbow method (K from 2 to 10).
7. **Trained K-Means** and gave each customer a cluster label.
8. **Studied each cluster** by its average age, quantity and total spend.
9. **Visualized** the clusters with scatter plots.

## Results

| Cluster | Segment | Customers | Avg Age | Avg Quantity | Avg Total | Share of Revenue |
|---|---|---|---|---|---|---|
| 0 | Older bulk buyers | 20,221 (20%) | 55.7 | 4.4 | 3,698 | 29.7% |
| 1 | Young light buyers | 20,657 (21%) | 31.0 | 1.5 | 561 | 4.6% |
| 2 | Young regular buyers | 27,054 (27%) | 30.1 | 3.9 | 2,606 | 28.0% |
| 3 | Older light buyers | 27,510 (28%) | 56.8 | 2.0 | 776 | 8.5% |
| 4 | Premium big spenders | 4,015 (4%) | 43.4 | 4.8 | 18,256 | 29.1% |

## Key Findings

- Cluster 4 is only **4% of customers**, but gives about **29% of the revenue**.
- Clusters 0, 2 and 4 together give about **87% of the revenue**.
- Clusters 1 and 3 are **49% of customers**, but give only about **13% of the revenue**.
- Age splits customers into a young group (around 30 years) and an older group (around 56 years).

## Business Suggestions

- Give clusters **0 and 4** loyalty rewards and early access to new products, so they stay.
- Give cluster **2** bundle offers and member offers to keep them buying.
- Give clusters **1 and 3** combo offers to increase the number of items they buy.

## Limitations

- Each customer bought only once, so RFM analysis was not possible.
- The elbow was not sharp, so K = 4 or 6 could also work.
- Only three features were used. Gender, payment method and category can be added next.

## Tech Stack

Python, Pandas, NumPy, Matplotlib, Scikit-learn, Jupyter Notebook

## How to Run

1. Download the dataset from Kaggle and keep both CSV files in the project folder.
2. Install the libraries: `pip install pandas numpy matplotlib scikit-learn`
3. Open `customer-segmentation-kmeans.ipynb` and run all cells.
4. If you run it locally, change the file paths in the first cell to your own folder.


**Suraj Vishwakarma**
[GitHub](https://github.com/Sunlight8169) | [LinkedIn](https://www.linkedin.com/in/suraj-vishwakarma-3088b7255)
