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
   
   1. customer_type
  
      There are 3 null values. In this column, I will check if the "member" value or the "normal" value appears more often to place the null value.
      
      <img width="167" height="92" alt="image" src="https://github.com/user-attachments/assets/b6064099-c7d5-4053-8b08-ba35f1b3d932" />

   2. product_category
  
      There are 6 null values.
      
       <img width="173" height="164" alt="image" src="https://github.com/user-attachments/assets/90b8f3f3-4a83-4ffe-8650-639b249adad6" />

      In this column, I will create a new sheet "Mapping", which includes 2 columns: "product_name" and "product_category". After that, I use Power Query to merge the Sheet "Sale" with the sheet "Mapping" through the primary key "product_name" => the null value will be replaced by the corresponding value.

        <img width="303" height="153" alt="image" src="https://github.com/user-attachments/assets/f1899559-aab9-4e09-94ae-bc621efd4ec9" />
        <img width="1081" height="377" alt="image" src="https://github.com/user-attachments/assets/50f53416-fde5-4118-acf5-bd02e55db1b2" />



   3. quantity
  
      There are 3 null values. In this column, I use the median function to fill in these 2 cells.
      
        <img width="162" height="90" alt="image" src="https://github.com/user-attachments/assets/b6ab2b84-0acd-4b11-a74b-28a5888564ab" />
        

   Data cleaning was conducted using Power Query in Microsoft Excel to ensure the dataset’s accuracy, completeness, and consistency before performing any analysis. The original dataset contained 12 missing values and 3 duplicate rows. Power Query provided a transparent and traceable workflow that effectively addressed these data quality issues.
          
  First, duplicate records were removed using the Remove Duplicates function, ensuring that each transaction represented a unique sale. Missing numerical values in the quantity column were imputed with the median value (11) to preserve the natural distribution of sales quantities. Missing categorical values in the customer_type column were replaced with the most frequent category (“Member”) to maintain consistency in customer classification. Missing values in the product_category column were accurately completed using a mapping table that linked each product name to its correct category, ensuring categorical consistency across the dataset.
    
  All cleaning steps were automatically documented in Power Query’s Applied Steps pane, providing a transparent audit trail of the transformations. After cleaning, the dataset contained no missing or duplicate entries.
