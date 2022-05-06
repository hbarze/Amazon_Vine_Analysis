# Amazon_Vine_Analysis
Module 16 Challenge: Big Data 

## Overview of the Analysis of the Vine Program: 
Since your work with Jennifer on the SellBy project was so successful, you’ve been tasked with another, larger project: analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

In this project, you’ll have access to approximately 50 datasets. Each one contains reviews of a specific product, from clothing apparel to wireless products. You’ll need to pick one of these datasets and use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, you’ll use PySpark, Pandas, or SQL to determine if there is any bias toward favorable reviews from Vine members in your dataset. Then, you’ll write a summary of the analysis for Jennifer to submit to the SellBy stakeholders.

# Deliverables: 
1. Perform an ETL on Amazon Product Reviews
2. Determine Bias of Vine Reviews
3. A written Report on the Analysis


Files: 
* This project used a pre-built SQL table schema and a google collaborate starter code for the Amazon ETL process
* I used the amazon_reviews_us_Video_Games_v1_00.tsv file to analyze. This dataset had 1,785,997 reviews. 

## Results:
After filtering the columns for reviews with 20 or more total votes, there were a combined 65,379 reviews with over 20 votes. 
<img width="694" alt="Screen Shot 2022-05-05 at 8 50 24 PM" src="https://user-images.githubusercontent.com/96043107/167058970-77edab13-fa7e-4496-82d4-2917a78059fe.png">


Next, I filtered the data to retrieve all rows where the number of helpful votes divided by the total votes is at least 50%. This amounted to 40,565 reviews. 
<img width="1216" alt="Screen Shot 2022-05-05 at 8 51 07 PM" src="https://user-images.githubusercontent.com/96043107/167059028-3ddd37e5-6b85-4a43-91df-7101fe8edff2.png">


I then filtered the data to show where a review was written as part of the paid Vine program. This amouunted to 94 reviews. 
<img width="954" alt="Screen Shot 2022-05-05 at 8 51 28 PM" src="https://user-images.githubusercontent.com/96043107/167059049-edef9791-bccb-4b8e-a6fb-85f6080764fc.png">

Next, I filtered the data to find all rows where the review was not part of the Vine program, i.e. filtering for the unpaid reviews, which amounted to 40,471 reviews. 
<img width="840" alt="Screen Shot 2022-05-05 at 8 53 18 PM" src="https://user-images.githubusercontent.com/96043107/167059208-6ceca352-f81d-4107-9343-442fdd2830fc.png">

I then created a variable to find the percentage of paid 5-star reviews, which was 48%. 
<img width="756" alt="Screen Shot 2022-05-05 at 8 54 37 PM" src="https://user-images.githubusercontent.com/96043107/167059301-67ff41a5-f5ea-4fbf-9d32-a72323c083db.png">

The next step was creating a variable to find the percentage of paid 5-star reviews, which was 51.06%. 
<img width="721" alt="Screen Shot 2022-05-05 at 8 56 17 PM" src="https://user-images.githubusercontent.com/96043107/167059418-261aee94-64f6-4374-b154-9491f6eeaadb.png">


Finally, the last step was creating another variable that found the percentage of unpaid (non-vine program) 5-star reviews, which was ~0.12%. 
<img width="735" alt="Screen Shot 2022-05-05 at 8 56 29 PM" src="https://user-images.githubusercontent.com/96043107/167059435-a617f5aa-1ab7-4cc7-9921-1fb416bbcc9c.png">


## Summary:

### Was there bias in the paid vine reviews? 
Just based off the last two variables I created, the paid 5-star review percentage (51%) vs. the unpaid 5-star review percentage (0.12%) it is clear there is bias within the paid vine reviews. However, the sample size for the paid vine reviews was only 94, while the sample size for the unpaid reviews was 40,471. 

### Additional analysis recommendation: 
To fully address the bias within the paid vine reviews, I would either seperate analyses similar to this one dealing with the video game reviews across the total 50 datasets provided for this module challenge, and then average the 5-star unpaid and paid review ratings to discover a better guage if the projects contain bias across all product review types, or only in certain categories. 
