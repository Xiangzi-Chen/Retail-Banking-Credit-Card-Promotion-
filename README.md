# Retail-Banking-Credit-Card-Promotion-Project

The real project I have done is entirely confidential, the content and data I used and shared on GitHub are all mocked for demonstration purposes only. This work sample is intended to showcase my logical thinking flow and the skills I have developed. It is not a representation of any real-world project or client work.

## Introduction

In today's highly competitive market, launching a new product can be a challenging task. It is crucial to identify the right merchant category and target the right segment of customers to make the product successful. In this project, one of the Canadian retail banks is aiming to launch a new product that focused on a specific merchant category. We will use data-driven insights and clustering techniques to identify various segments of customers within the data and determine which segment to target for this new product.

## Project Overview

* Develop a new product focused on a specific merchant category. (Task 1)
* Identify and describe various segments of customers within the data using segmenting/clustering techniques. (Task 2)
* Determine which specific segment to target for the new product and explain the rationale for the choice. (Task 3)
* Consider potential challenges and risks associated with targeting the chosen segment compared to other segments. (Task 4)

## Dataset

There are 3 datasets related to the credit card transaction.

BusinessCase_Custs.csv: This dataset contains information about the customers, including their gender, birth date, work activity, occupation industry, income, relationship status, habitation status, address, and school. This dataset can be used to identify different customer segments based on their demographics and lifestyle.

BusinessCase_Accts.csv: This dataset provides information about the customer's account, including their branch number, account type, open date, account id, balance, currency, and customer id. This dataset can be used to understand the customer's financial behavior and transaction patterns.

BusinessCase_Tx.csv: This dataset contains transaction records between 2018-01-01 and 2018-12-31, including transaction description, currency amount, location (all null), origination date and time, customer id, merchant id, account id, and category tags (transaction category). This dataset can be used to identify the merchant category that the new product should target and also to understand the transaction patterns of different customer segments.


(Dim_Customer.csv: Customer information including gender, birth date, age group, work activity, total income, relationship status, habitation status, emoloyment industry id and emoloyment industry name.

Dim_account.csv: Customer account information for who open the account on 2018-03-01, dataset including their branch number, open date, account id, open balance, and customer id.

Fct_Txn_Acct.csv: Spend records between 2018-01-01 and 2018-12-31, inclduing transaction date, account id, customer id, merchant id, category tags, transaction description, spend amount.

Rl_Cust_Seg.csv

Fct_Txn_Cust.csv: Spend records between 2018-01-01 and 2018-12-31, inclduing transaction date, customer id, merchant id, category tags, transaction description, spend amount, year quarter, last quarter and ll quarter.)

## New product development

### Data Cleaning

To gain insights into the market and determine the specific merchant category for the new product, we analyzed transaction data from the BusinessCase_Tx.csv dataset, which contains transactions from March 2018 to October 2018. However, I observed that the merchantId column had missing data, with approximately 53.1% of values missing, and CategoryTags had around 0.16% missing values. Since the primary objective was to identify the specific merchant category for the bank's new product, we recognized that the category tags could be a crucial factor in our investigation. Therefore, I examined the transactions with missing category tags and discovered that they were all related to paying payday loans, which is a short-term, high-interest loan typically provided by non-bank financial institutions or lenders. As a result, I assigned the merchant category for these transactions with the tag 'Loan'.

### Data exploration and analysis

To successfully launch a new product focused on a specific merchant category for a bank, it is important to carefully consider the type of card that will be offered. Between credit cards and debit cards, credit cards are generally preferred for merchant category-specific products due to the additional benefits and protections they offer, such as purchase protection, extended warranties, and rewards programs. Credit cards also provide consumers with the option to finance their purchases over time, which can be beneficial for more expensive items.

When launching a credit card product, there are four ways in which credit card companies can make a profit: interest on balances, fees, interchange fees from merchants, and rewards programs that incentivize people to use the card more often. These profit avenues will be kept in mind as we explore our transaction data to determine the specific merchant category for the new product.

To gain a comprehensive understanding of the transaction data and establish a foundation for analysis, we will provide some insights of the transactions across different categories, which will enable us to identify the notable trends or patterns. Also, we will conduct a thorough analysis of the transaction data to gain insights and identify the optimal merchant category. Our examination will focus on determining the most popular merchant categories, assessing the frequency of transactions for each category and analyzing average transaction amounts. These insights will serve as a foundation for making informed decisions regarding the specific merchant category to target with the new product.

I will begin by providing an overview of the transactions across different categories, which will allow us to gain valuable insights into the distribution and magnitude of transactions in each category.

1) The overview of the number of transactions for different categories.

![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/63ad0744-89d9-4b8e-a8a7-0f0955677dc6)

The graph above reveals that the majority of transactions are allocated to categories such as Transfer, Income, Bills and Utilities, and Food and Dining. This observation is in line with expectations, as these categories represent essential and recurring transactions in customers' daily lives.

The overview of the transactions amount for different categories.
![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/1a9597fe-f398-46d5-88ac-59dd4ff484cb)

The graph above provides an overview of the transaction amounts for different categories. From the graph, we can observe that the leading categories in terms of the total value of transactions are Income, Transfer, Taxes, Mortgage and Rent, and Bills and Utilities. These categories play a significant role in customers' financial activities and daily expenses.

To delve deeper into the transaction data, we will now investigate the frequency of transactions for each transaction category tag in every month.

2) The transaction frequency for different transaction category tags in every month

![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/78a3b510-4f82-4db6-9d99-5312441ea1e8)

![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/81a44f75-20bf-4cc7-b2ed-2be8e2de41be)

![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/83e2a85d-4084-4ca8-ab96-881839dc54c1)

![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/1258332f-f4f2-4c6b-99bc-8d94a227e927)

Based on the analysis of the transaction data, it is evident that certain merchant categories, such as Transfer, Taxes, Bills and Utilities, and Food and Dining, consistently exhibit high transaction amounts across almost every month. This finding is expected, as these categories encompass essential and recurring transactions in consumers' daily lives. However, while these categories have high transaction volumes, they may not be suitable for the new product as they do not encourage customers to use the credit card more frequently. This could limit the potential profitability for the credit card company. As a result, our focus should shift towards other merchant categories that offer greater potential for the bank to introduce a new product. Also, for category 'Mortgage and Rent', although it represents a significant expense for many individuals, it may not serve as an ideal focus for the new product, given the nature of these transactions and the limited scope for encouraging increased card usage.

To focus on merchant categories that present potential opportunities for the bank's new product, I have eliminated these commonly observed categories from consideration.

Then, I have generated graphs showcasing the ranking of total transaction values for each remaining category on a monthly basis to identify the discernible trends or patterns in consumer spending behavior for specific merchant categories over time.

![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/a77613c2-68cc-43ae-abf0-3fc006652efa)
![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/af0e8cfb-94ab-4845-8997-045f9ffa7d74)
![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/bc4d5377-6f60-42e5-8a80-fdec20132144)
![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/c1446bbe-8bed-4b38-85a6-04e48ff576d9)

Based on the rank for the total transaction value for each category on each month, we can see that loan and travel take the leading places. Transaction with category 'Loan' is the category we set for payday loan. While credit card companies have the flexibility to launch products targeting various segments, focusing on payday loans may pose challenges and ethical considerations. Payday loans are often associated with high-interest rates and are primarily utilized by individuals facing financial difficulties or limited access to traditional banking services. It is also typically intended for short-term borrowing needs, which may not align with the typical payment structure of credit cards. This leading us to focus on another category, Travel. For most of the months, the total value of transactions on travel takes the top position in all of the merchant categories. This suggests that travel may be the category to focus on for the new product.

Moreover, we investigated the average value per transaction for each category and found that travel has the highest average value per transaction except the category 'Loan'. As one of the main ways for credit card companies to make a profit is through the interchange fee per transaction charged from the merchant, we can see that travel is not only a category that can boost customer consumption but also a profitable category for the bank.

![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/690f8fd0-f90d-4afc-8a31-b0ff744f61b7)

Furthermore, the fact that only 85 existing customers have used the travel product for the bank suggests that there is a large untapped market for promoting travel credit cards. By understanding the needs and preferences of potential customers in this category and offering tailored benefits and rewards, we can attract new customers and drive revenue growth for the bank.

![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/f39aab65-983f-4135-9fc0-e52d451c20ff)

In conclusion, our analysis of the transaction data allowed us to narrow down our focus to the most profitable merchant categories. By eliminating certain transaction categories and considering the total transaction value and average value per transaction, we have identified the travel category as a promising strategy for the new product. This category shows potential for increasing customer consumption and generating substantial profits through interchange fees charged to merchants. By targeting the travel category, we can align our product offering with customer preferences while maximizing profitability for the bank.

### Thoughts
#### Task 1
1. check the total amount and count of each category (checked)
2. see the number of categories for each customer, want to eliminate the propability that same person made huge number of same type transaction
3. see the time change (count) for different category, the merchant we want to focus should have stable transaction amount in each month.
4. decide the key metrics: total value/total amount
5. avarage value/amount per customer for each category
6. questions:
  1) the most important thing that bank values (total value?)
  2) is transfer counted as a merchant category for bank
  3) how to differicate the specific usage for transfer


