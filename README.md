# DSA-DATA-ANALYSIS-CAPSTONE-PROJECT(EXCEL)
This is my first project as a data analyst under DSA. I am not perfect, but I am learning and aiming to improve as I embark on this new journey.

## Case Study 1: Amazon Product Review Analsis

## Task Given 
As a junior data analyst, I was tasked with analyzing product and customer review data to generate insights that can guide product improvements, marketing strategies, and customer engagement. This involved creating a cleaned dataset, generating pivot outputs, and building an Excel dashboard.


## Question and solution used to analyse operations.
1. Average discount percentage by product category
Add a calculated column:
= (Actual Price - Discounted Price) / Actual Price * 100

Then use a Pivot Table:
Rows: Category
Values: Discount % → summarize by Average 

2. How many products are listed under each category
Pivot Table:
Rows: Category
Values: Product Name → set to Count (Distinct) 

3. Total number of reviews per category
Use Rating Count column
Pivot Table:
Rows: Category
Values: Rating Count → Sum 

4. Which products have the highest average ratings
Sort your dataset by the Average Rating column (descending)
Pick top entries 

5. Average actual price vs discounted price by category
Pivot Table:
Rows: Category
Values: Actual Price → Average
Discounted Price → Average 

6. Which products have the highest number of reviews
Sort Rating Count column in descending order

7.How many products have a discount of 50% or more
Add calculated column:
=IF(Discount % >= 50, "Yes", "No")
Then use a COUNTIF 

8. Distribution of product ratings
Pivot Table:
Rows: Rating (rounded if needed)
Values: Product Name → Count.  

9. Total potential revenue by category (Actual Price × Rating Count)
Add calculated column:
=Actual Price * Rating Count
Pivot Table:
Rows: Category
Values: Potential Revenue → Sum 

10. Number of unique products per price range bucket
Create new column Price Bucket:
Excel formular=IF(Discounted Price < 200, "<₹200",
   IF(Discounted Price <= 500, "₹200–₹500", ">₹500")) (they should take note of the symbol for some systems)
Pivot Table:
Rows: Price Bucket
Values: Product Name → Count 

11. How does the rating relate to the level of discount
Create a scatter chart:
X-axis: Discount %
Y-axis: Average Rating. (i am not sure if all excel version has scatter chat.).   alternative to scatter chat, this is a longer route thou. (take your time and you'll get it.) Line Chart (Grouped by Discount Ranges)
Steps:
Create a new column that groups Discount % into buckets like:
0–10%, 11–20%, ..., 91–100%
excel formular=IF([@Discount%]<=10, "0-10%",
  IF([@Discount%]<=20, "11-20%",
  IF([@Discount%]<=30, "21-30%", ...)))
Use a Pivot Table:

Rows: Discount Bucket
Values: Average Rating → summarize as Average
Insert a line chart to show trend of average rating across discount buckets 

12. How many products have fewer than 1,000 reviews
Filter Rating Count < 1000
Use COUNT or check the status bar, count is there. 

13. Which categories have products with the highest discounts
Use the earlier Discount % column
Pivot Table:
Rows: Category
Values: Discount % → Max 

14. Top 5 products by rating + number of reviews combined
Create calculated column:
=Average Rating + (Rating Count / Scaling Factor)
(Choose a factor like 1000 to balance weight)
Sort descending and pick top 5.
