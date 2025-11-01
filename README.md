MIS311 – Data Analysis Project

**Dataset:** Supermarket Sale  
**Student:** Vu Dong Duong  
**University:** Eastern International University

1. Data Overview

The Supermarket Sale dataset contains detailed transaction records from a retail supermarket chain operating across multiple branches and cities. Each entry represents an individual purchase and includes information such as the branch, city, customer type, product name, product category, quantity purchased, and total sales amount in USD.
     
      •	Sale_id (object): Unique identifier
      
      •	Branch (object): brand of the supermarket
      
      •	City (object): city of the supermarket
      
      •	Customer_type (object): Type of customers
      
      •	Product_name (object): Name of product
      
      •	Product_category (object): Category of product
      
      •	Quantity (int): amount sold
      
      •	Total_price (float64): amount of sales in USD

The dataset comprises 253 rows and 8 columns, featuring both categorical variables (branch, city, customer_type, product_category) and numerical variables (quantity, total_price). This combination offers a clear and practical perspective on day-to-day retail operations and customer spending behaviors, making the dataset ideal for exploratory data analysis within a business analytics context.

  <img width="649" height="101" alt="image" src="https://github.com/user-attachments/assets/0d1731b5-7067-481a-bc42-c0b1382c97bc" />
  <img width="649" height="108" alt="image" src="https://github.com/user-attachments/assets/82f1b4d7-d90b-4b53-a77d-06af857aaaca" />

This dataset was chosen because it illustrates how businesses can use data analytics to uncover patterns in sales performance, identify profitable customer segments, and support data-driven decisions in marketing and inventory management.

2. Data Cleaning

I use Powery Query to check missing values and remove duplicate values
   
   2.1. customer_type
    
  There are 3 null values. In this column, I will check if the "member" value or the "normal" value appears more often to place the null value.
      
<img width="167" height="92" alt="image" src="https://github.com/user-attachments/assets/b6064099-c7d5-4053-8b08-ba35f1b3d932" />

   2.2. product_category
   
  There are 6 null values.
      
<img width="173" height="164" alt="image" src="https://github.com/user-attachments/assets/90b8f3f3-4a83-4ffe-8650-639b249adad6" />

  In this column, I will create a new sheet "Mapping", which includes 2 columns: "product_name" and "product_category". After that, I use Power Query to merge the Sheet "Sale" with the sheet "Mapping" through the primary key "product_name" => the null value will be       replaced by the corresponding value.

<img width="303" height="153" alt="image" src="https://github.com/user-attachments/assets/f1899559-aab9-4e09-94ae-bc621efd4ec9" />
<img width="1081" height="377" alt="image" src="https://github.com/user-attachments/assets/50f53416-fde5-4118-acf5-bd02e55db1b2" />

   2.3. quantity
  
  There are 3 null values. In this column, I use the median function (median = 11 )to fill in these 2 cells.
      
<img width="162" height="90" alt="image" src="https://github.com/user-attachments/assets/b6ab2b84-0acd-4b11-a74b-28a5888564ab" />
        
Data cleaning was conducted using Power Query in Microsoft Excel to ensure the dataset’s accuracy, completeness, and consistency before performing any analysis. The original dataset contained 12 missing values and 3 duplicate rows. Power Query provided a transparent and traceable workflow that effectively addressed these data quality issues.
          
First, duplicate records were removed using the Remove Duplicates function, ensuring that each transaction represented a unique sale. Missing numerical values in the quantity column were imputed with the median value (11) to preserve the natural distribution of sales quantities. Missing categorical values in the customer_type column were replaced with the most frequent category (“Member”) to maintain consistency in customer classification. Missing values in the product_category column were accurately completed using a mapping table that linked each product name to its correct category, ensuring categorical consistency across the dataset.
    
All cleaning steps were automatically documented in Power Query’s Applied Steps pane, providing a transparent audit trail of the transformations. After cleaning, the dataset contained no missing or duplicate entries.

3. Descriptive Statistics

  <img width="480" height="323" alt="image" src="https://github.com/user-attachments/assets/b3823151-7c52-4c9a-9ebe-81f62fb44c3d" />

For the Quantity variable, the data shows that customers purchased an average of 10.62 items per transaction, with a median of 11. This means that most customers typically bought around ten to eleven items each time they visited the store. The smallest transaction included 1 item, while the largest reached 20 items, showing clear variation in shopping size. The standard deviation of 5.99 indicates moderate variability in purchase quantities, suggesting that some customers buy far more items than others. The skewness value (-0.07), which is close to zero, shows that the quantity distribution is fairly balanced between small and large purchases.
     
For the Total Price variable, the average sales value per transaction was $124.19, and the median was $95.43. This result shows that half of all transactions were below $95 and the other half were above it. The smallest transaction value was $2.18, while the largest reached $427.14, revealing a wide range of customer spending levels. The standard deviation of 102.98 highlights significant variation in sales amounts. The positive skewness (0.91) suggests that a few high-value purchases increased the overall average, meaning that while most transactions were moderate, a small number of expensive purchases significantly boosted total revenue.

  Chart 1: Number of Transactions by Customer Type

<img width="490" height="314" alt="image" src="https://github.com/user-attachments/assets/0f17eb72-402e-48d3-99cd-a0998dd8ccee" />

  The chart shows the number of sales transactions made by each customer type. Members recorded 134 transactions, higher than Normal customers with 116 transactions. This indicates that members contribute more actively to the supermarket’s overall sales volume.

  Chart 2: Number of Transactions by Product Category

 <img width="479" height="306" alt="image" src="https://github.com/user-attachments/assets/fb0eb01d-0919-4be3-923a-00798667767c" />

  The chart shows the number of sales transactions across different product categories. Fruits recorded the highest number of sales (58), followed closely by Household items (57) and Beverages (49). In contrast, Personal Care products had the fewest transactions (42).
  This pattern suggests that everyday consumer goods such as fruits and household products, are the most frequently purchased items in the supermarket.

