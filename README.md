# Amazon Review Analysis
## Overview of the Analysis
In this project, cloud Extract, Transform, Load (ETL) process is performed on [Amazon Review Datasets](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt) using the following tools:<br>
- Language: PySpark<br>
- Software: Amazon Web Service (AWS), pgAdmin, PostgreSQL, Google Colab Notebook

The ETL process is applied as follow:<br>
1. Choosed a dataset from [Amazon Review Datasets](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt). In this project, [Musical Instruments](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Musical_Instruments_v1_00.tsv.gz) product is selected.
2. Created a new AWS relational database on the Amazon website.
3. Connected pgAdmin to RDS instance.
4. Created tables for database In pgAdmin (run [schema.sql](https://github.com/elp192/Amazon-Review-Analysis/blob/d1fec506dbb3d9b8c7a0cfa16f6e925da960422c/schema.sql)).
5. Created a new Google Colab Notebook ([Amazon_Reviews_ETL.ipynb](https://github.com/elp192/Amazon-Review-Analysis/blob/df5a941da1dcdb3e450e1466e77e2c1971da4fe6/Amazon_Reviews_ETL.ipynb)) and performed the following steps:<br>
   - Installed PySpark in Google Colab and started Spark session.<br>
   - Extracted a selected database and created a DataFrame.<br>
   - Transformed the dataset into the 4 Dataframes to match the table created in step 4 in Pgadmin.<br>
   - Connected to AWS RDS instance and loaded (written) DataFrames to their corresponding table in RDS.<br>
   - Run queries in pgAdmin to check whether the tables are populated.<br>

Note: In the Amazon_Reviews_ETL.ipynb file, sensitive data (i.e., password and connection strings) are removed. To run the file, it is necessary to add the password and connection strings.

Amazon Vine service provides manufacturers with reviews from customers for their products and asks manufacturers to pay a fee to Amazon.
Using the [Musical_Instruments](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Musical_Instruments_v1_00.tsv.gz) dataset, we want to conclude that whether there is a bias toward reviews that were received from Vine program. In doing so, the percentage of 5-star reviews between paid (Vine) reviews and unpaid (non-Vine) reviews are compared.<br>
