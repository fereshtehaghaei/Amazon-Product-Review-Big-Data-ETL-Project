# "Alexa, can you handle Big Data?" (ETL)



## Background

Many of Amazon's shoppers depend on product reviews to make a purchase. Amazon makes these datasets publicly available. However, they are quite large and can exceed the capacity of local machines to handle. One dataset alone contains over 1.5 million rows; with over 40 datasets, this can be quite taxing on the average local computer. The goal of this project was to perform the ETL process completely in the cloud and upload the DataFrame to an RDS instance. The second goal was to use PySpark or SQL to perform a statistical analysis of the selected data.

https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Books_v1_02.tsv.gz
https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Beauty_v1_00.tsv.gz

1. Created DataFrames to match production-ready tables from two big Amazon customer review datasets: beauty and book

2. Analyzed whether reviews from Amazon's Vine program are trustworthy.

   

## Level 1

- Created tables in a RDS database.
- Created two separate Google Colaboratory notebooks and **Extracted** the beauty and book datasets from the list at [review dataset](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt), one into each notebook.
- For each dataset, I completed the following:
  - Counted the number of records (rows) in the dataset.
  
  - **Transformed** the dataset to fit the tables in the [schema file](https://github.com/willcpope/big-data-challenge/blob/master/level-1/schema.sql).
  
  - Created two different Data Base postgres, postgres2 (one for beauty & one for books), in order to keep the same code
  
  - **Loaded** the DataFrames that correspond to tables into an RDS instance.
  
    

## Level 2

In Amazon's Vine program, reviewers receive free products in exchange for reviews.

[![vine01.png](https://github.com/willcpope/big-data-challenge/raw/master/Images/vine01.png)](https://github.com/willcpope/big-data-challenge/blob/master/Images/vine01.png)

Amazon has several policies to reduce the bias of its Vine reviews: https://www.amazon.com/gp/vine/help?ie=UTF8.

Investigated whether Vine reviews are free of bias. Used PYSPARK to analyze the data. The conclusion is Vine reviews are helpful and trustworthy. This analysis was done for beauty products by looking at helpful votes and five star reviews. It was hard to do analysis for books since there were only two 'Y' vines. 



### Copyright

Fereshteh Aghaei © 2021. All Rights Reserved.