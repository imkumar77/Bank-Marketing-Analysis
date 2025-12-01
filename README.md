# Bank-Marketing-Analysis

## Objective
The objective of this project is to identify which existing customers are most likely to open a term deposit account. The analysis focuses on understanding the factors that influence customer conversions during the 2017 telemarketing campaign. By finding these driver variables and customer patterns, the goal is to help the bank plan future campaigns in a more efficient and cost-effective way.

Here is a clean and direct **Problem Statement** for your GitHub report:

---

## Problem Statement

The Bank of Corporate ran a telemarketing campaign in 2017 to promote term deposits among its existing customers. While the campaign generated responses, the bank does not clearly understand which customers are most likely to convert or which factors influence the success of such campaigns. Without this clarity, future marketing efforts may lead to high costs and low returns.

The problem is to analyse the campaign dataset, uncover the patterns that drive customer conversions and build an optimised approach that can guide the bank in targeting the right customers for future term deposit campaigns.

Here is a simple and clear **Approach** section for your GitHub report:

---

## Approach

1. **Data Understanding**
   Started by reviewing the dataset to understand the structure, variable types and data quality. Checked for missing values, outliers and inconsistencies.

2. **Exploratory Data Analysis (EDA)**
   Explored customer demographics, account information and campaign-related variables. Looked for patterns, relationships and trends that might influence whether a customer opens a term deposit.

3. **Feature Analysis**
   Identified key driver variables by studying how different factors such as age, job type, balance, campaign duration and previous interactions affect the conversion rate.

4. **Segmentation of Potential Customers**
   Grouped customers based on behaviour and characteristics to understand which segments have a higher likelihood of converting.

5. **Optimisation Insights**
   Used insights from EDA to propose an optimised strategy for targeting the right customers in future campaigns, focusing on reducing costs and improving conversion rates.

6. **Final Recommendations**
   Summarised findings and provided data-backed suggestions for building a more effective marketing plan for term deposits.

---
- **Data Understanding**
  
Account no	Age	Job	Marital Status	Loan Default	Housing Loan	Personal Loan	Education	Cash Balance	Contact	pdays	previous	poutcome	Subscription	Date	Call Duration
<img width="1634" height="25" alt="image" src="https://github.com/user-attachments/assets/62034986-112c-4c10-8353-0f03fb49e34a" />

- **Data Dictionary**

<img width="860" height="1033" alt="image" src="https://github.com/user-attachments/assets/b38eb170-e34d-4895-b4ac-84908551de0d" />

## Exploratory Data Analysis (EDA)
1. Age Column

While analysing the age variable, several records showed negative values. Since age cannot be negative, these values were corrected using the absolute value formula:
=ABS(B1)
This ensured all age values were valid.

2. Job Titles

The job column had inconsistent entries such as “admin” and “admin.” (with a dot). These referred to the same job role, so they were standardised by replacing “admin.” with “admin”.

3. Missing Values

A few columns had many missing entries, especially for fields based on Yes or No responses. Instead of filling these values inaccurately, the entire column was removed to maintain the quality of the dataset.

4. Duplicate Records

A total of 142 duplicate rows were identified in the dataset. These were removed to avoid repeated customer information and to ensure a clean dataset for analysis.

5. Categorical to Numerical Conversion

Columns containing Yes and No values were converted into numerical form to make the data suitable for further analysis and modelling.

Yes → 1

No → 0

6. Date Formatting

The date column contained combined day, month and year information. These were extracted into separate columns for better analysis.

```excel
Day: =LEFT(O2,1)

Month: =MID(O2,3,3)

Weekday: =TEXT(O2,"dddd")
```

7. Call Duration

The call duration was in a text format such as “0 hrs 4 mins 21 secs”. To analyse it properly, the duration was split into hours, minutes and seconds.
```Excel
Hours: =LEFT(P2,1)

Minutes: =MID(P2,7,2)

Seconds: =MID(P2,14,2)

```

These were combined into a time value:
=TIME(Q2, R2, S2)

Finally, the time was converted into total seconds using:
=T2*86400

This helped in understanding the impact of call length on customer conversions.

## Univariate Analysis

```
<img width="1726" height="450" alt="image" src="https://github.com/user-attachments/assets/c883aa56-e6dd-49ed-9d7c-4498d74970c0" />
```
Observation: 
As we can see, the majority of customers lie between 24-60. This can be considered the most effective working group. We can also observe a steep decline in customers after 60.





  

