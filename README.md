# Amazon_Vine_Analysis
## Overview:
- The purpose of this analysis was to analyze product reviews of a given dataset. The dataset that was chosen for this project was an Amazon Review dataset on major appliances. With the dataset we compared paid(Vine) and unpaid reviews and specifically looked at how each type of review affected the 5-star reviews. The following tools were used in the analysis:
    - Amazon Web Services(AWS): 
        - RDS- Managed Relational Database Service
        - S3- Scalable Storage in the Cloud
    - Google Colab Notebooks
    - PySpark
    - PgAdmin- Used for Postgres Databases

## Results:
- In order to do the analysis on the reviews, the original data was read into a DataFrame using PySpark, and then filtered multiple times. The original DataFrame was filtered to only focus on specific columns of data to show information related to the product reviews. Below is an image showing the original reviews DataFrame, which I called Vine_df.
![Original Reviews DataFrame](/Images/Original_Review_DataFrame.png)
**Original reviews DataFrame with all the review data.**

- Next we filtered that DataFrame to only include data where the total_votes were greater than or equal to 20 in order to use reviews that were more likely to be helpful. This could also help us avoid skewed data and creating errors later on in the analysis. Below is an image of this filtered DataFrame.
![First Filter of the Reviews DataFrame](/Images/First_Filtered_Version_Review_DataFrame.png)
**Initial filter on the reviews DataFrame, and total row count for the DataFrame**

- The next filter was added to create a DataFrame where we only showed data that included data where the total number of helpful_votes/total_votes was equal to or greater than 50 percent, to trim the data a little more. Below is an image of this filtered DataFrame.
![Second Filter of the Reviews DataFrame](/Images/Second_Filtered_Version_Review_DataFrame.png)
**Additional filter on the reviews DataFrame, and the total row count for the DataFrame**

- In order to view the data that only pertained to the vine(paid) reviews, we filtered the second filtered version of the review DataFrame to only show data where the vine column was equal to 'Y'. Below is an image of the vine(paid) reviews DataFrame.
![Vine(paid) Reviews DataFrame](/Images/Vine_Review_DataFrame.png)
**Vine(paid) reviews DataFrame**

- In order to view the data that only pertained to the non-vine(unpaid) reviews, we filtered the second filtered version of the review DataFrame to only show data where the vine column was equal to 'N'. Below is an image of the non-vine(unpaid) reviews DataFrame.
![Non-vine(unpaid) Reviews DataFrame](/Images/Non_Vine_Review_DataFrame.png)
**Non-vine(unpaid) reviews DataFrame**

- Using the above DataFrame, we found the following results:
    - Vine(paid) data findings:
        - Total vine(paid) reviews: 35
        - Total vine(paid) 5-star reviews: 18
        - Percentage of vine(paid) 5-star reviews: 51.43%
    - Non-vine(unpaid) data finding:
        - Total non-vine(unpaid) reviews: 4957
        - Total non-vine(unpaid) 5-star reviews: 1963
        - Percentage of non-vine(unpaid) 5-star reviews: 39.6%

## Summary:
- According to the results, it does appear that there is a positivity bias for reviews in the Vine program as over half the reviews in the Vine program were 5 star reviews. Although the Vine program does show a positivity bias which could potentially skew the number of 5 star reviews for particular products, it may not cause an overall effect on the ratings of a particular item. Another analysis that could be done to support my findings is one that shows the percentage of total vine(paid) reviews in the total reviews dataset, and the percentage of total non-vine(unpaid) reviews in the total reviews dataset. This could show just how utilized the Vine program is by companies, which could reveal the accuracy/inaccuracy of the overall rating for a particular product.