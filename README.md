# Superstore-Sales-Analysis

## Business Context

While customer's demand and intense competition in the market are rising, understanding sales performance and profitability drivers is essential for retail businesses to make informed strategic decisions. This project analyzes transactional sales data from a Superstore Giant to identify revenue trends, profit performance, and underperforming product categories as well as which customer segment should be target or avoid.

The goal is to evaluate overall business performance and provide insights to support **pricing strategy** and **profitability improvement.**

## Dataset: Superstore

Dataset URL: https://www.kaggle.com/datasets/vivek468/superstore-dataset-final?resource=download

The dataset contains **10,000 records** information related to sales, profit and other interesting fact of Superstore Giant including: 

**Order ID** - Unique Order ID for each Customer.

**Order Date** - Order Date of the product.

**Ship Date** - Shipping Date of the Product.

**Ship Mode** - Shipping Mode specified by the Customer.

**Segment** - The segment where the Customer belongs.

**Country** - Country of residence of the Customer.

**City** - City of residence of of the Customer.

**State** - State of residence of the Customer.

**Region** - Region where the Customer belong.

**Product ID** - Unique ID of the Product.

**Category** - Category of the product ordered.

**Sub-Category** - Sub-Category of the product ordered.

**Product Name** - Name of the Product

**Sales** - Sales of the Product.

**Quantity** - Quantity of the Product.

**Discount** - Discount provided.

**Profit** - Profit/Loss incurred.

**Note:** Some identifier columns such as **Row ID, Customer Id, Customer Name, Postal Code** were removed during data cleaning because they do not provide meaningful predictive information as well as to ensuring customer's privacy.

## Tools Used

- Python (Pandas, NumPy, Seaborn, Matplotlib, Statsmodels)
 
- Power BI
  
- DAX (Data Analysis Expressions)

- Jupyter Notebook

## Data Preparation

The dataset was processed and prepared before visualization:

- Checked missing values and data types
  
- Converted categorical variables 

- Created calculated measures (Revenue, AOV, Profit Margin, Order Count)
  
- Built correlation heatmap to understand relationships between Sales, Profit, Quantity, and Discount

- Prepared feature variables for regression modeling

## Dashboard Overview

The Power BI dashboard provides an interactive overview of sales performance across regions, customer segments, and product categories: 

<img width="1413" height="793" alt="image" src="https://github.com/user-attachments/assets/57ae04bc-a539-4fbf-bf07-161d51791d81" />

**Key Insights:**

- **Revenue** were **stagnant** between 2014 and 2015, however after 2015, it grows **tremendously** indicating strong business growth
  
- Overall **profit margin** remains relatively low at **2.89%**, suggesting opportunities for **improvement** via better **pricing control** and **margin management**
  
- Several **sub-categories** including **Tables, Bookcases, and Supplies** generated **negative profit** might implying structural **pricing/ discount strategy issues**
  
- The **Furniture** category generates the **lowest profit** across all regions, with a **loss of $3,000** in the Central region, suggesting **potential issues** in **pricing strategy** or **discount management** for this category.

## Correlation Analysis

<img width="776" height="682" alt="image" src="https://github.com/user-attachments/assets/fe677d01-6300-4563-9e1a-5fd20fe12577" />

- Correlation analysis shows a moderate positive relationship between Sales and Profit (0.48), indicating revenue growth contributes directly to profitability

- Discount has a negative correlation with profit (-0.22), suggesting that excessive discounting reduces profitability and should be applied strategically rather than broadly

- Quantity has only a weak relationship with profit (0.066), implying that selling more units alone does not necessarily increase earnings unless supported by strong pricing and margin control.

-> Overall, the results highlight that optimizing pricing strategy and controlling discount levels are more impactful for improving profitability than increasing sales volume alone.

## Regression Modeling

A multiple linear regression model was developed to analyze factors influencing profitability. 

Independent variables included:

- Price
  
- Quantity

- Discount

- Region

- Category

- Sub-category

The dataset was split into training (70%) and testing (30%) subsets to evaluate model performance and reduce overfitting risk. Hence, insignificant features were excluded based on P-value: 

<img width="668" height="666" alt="image" src="https://github.com/user-attachments/assets/9ec92c9e-478d-42fc-8144-31e9a7e86154" />

The regression results indicate that Price has a strong positive relationship with Profit, while Discount negatively impacts profitability. Several sub-categories also show statistically significant influence on profit performance.

-> The model achieved an **R-squared (training) ** value of approximately **0.44**, indicating that the selected variables explain a moderate proportion of variation in profit.

## Model Evaluation:

The following metrics were calculated: 

- R-squared (Testing)

- Mean Absolute Error (MAE)

- Root Mean Squared Error (RMSE)

<img width="654" height="325" alt="image" src="https://github.com/user-attachments/assets/1606a460-58bf-42fc-8855-ac5af42c875c" />

- The regression model produced a **MAE** of approximately **$64.11**, meaning that **predicted profit** values **differ** from actual outcomes by **around $64** per transaction on average.

- **RMSE** accounted for **$235.66** indicates the presence of larger prediction errors in certain cases

- The **negative R-squared score (-0.03)** on the testing dataset suggests that the model **does not generalize** well to unseen data, highlighting the complexity of profit prediction in retail environment and the need for additional feature engineering or alternative modeling approaches. It also influenced by additional factors not captured in the current feature set.

## Business Recommendations

Based on the analysis, the company should: 

1. Optimize **discount policies** across underperforming sub-categories, particularly **Tables, Bookcases, and Supplies**, where high discount levels contribute to negative profit

2. Reassess pricing strategies for the **Furniture category**, especially in the Central region

3. Expand focus on high-margin categories such as **Technology** to further improve overall profitability

4. Shift **strategic emphasis** from **volume-driven growth** toward **margin-driven performance** improvement

5. Monitor sales performance **across regions** to identify underperforming areas and **adjust pricing** or **discount strategies** accordingly
