# Retail-Banking-Credit-Card-Promotion-Project

The real project I have done is entirely confidential, the content and data I used and shared on GitHub are all mocked for demonstration purposes only. This work sample is intended to showcase my logical thinking flow and the skills I have developed. It is not a representation of any real-world project or client work.

## Introduction

In today's highly competitive market, launching a new product can be a challenging task. It is crucial to identify the right merchant category and target the right segment of customers to make the product successful. In this project, one of the Canadian retail banks is aiming to launch a new product that focused on a specific merchant category. We will use data-driven insights and clustering techniques to identify various segments of customers within the data and determine which segment to target for this new product.

## Project Overview

* Develop a new product focused on a specific merchant category.
* Identify and describe various segments of customers within the data using segmenting/clustering techniques.
* Determine which specific segment to target for the new product and explain the rationale for the choice.
* Consider potential challenges and risks associated with targeting the chosen segment compared to other segments.

## Dataset

There are 3 datasets related to the credit card transaction, which describes 

BusinessCase_Custs.csv: Customer information including gender, birth date, work activity, occupation industry, income, relationship status, habitation status, address and school.

BusinessCase_Accts.csv: Customer account information for who open the account on 2018-03-01, dataset including their branch number, account type, open date, account id, balance, currency, and customer id.

BusinessCase_Tx.csv: Transaction records between 2018-01-01 and 2018-12-31, inclduing transaction description, currency amount, location (all null), origination date and time, customer id, merchant id, account id and category tages (transaction category).

BusinessCase_Custs.csv: This dataset contains information about the customers, including their gender, birth date, work activity, occupation industry, income, relationship status, habitation status, address, and school. This dataset can be used to identify different customer segments based on their demographics and lifestyle.

BusinessCase_Accts.csv: This dataset provides information about the customer's account, including their branch number, account type, open date, account id, balance, currency, and customer id. This dataset can be used to understand the customer's financial behavior and transaction patterns.

BusinessCase_Tx.csv: This dataset contains transaction records between 2018-01-01 and 2018-12-31, including transaction description, currency amount, location (all null), origination date and time, customer id, merchant id, account id, and category tags (transaction category). This dataset can be used to identify the merchant category that the new product should target and also to understand the transaction patterns of different customer segments.


(Dim_Customer.csv: Customer information including gender, birth date, age group, work activity, total income, relationship status, habitation status, emoloyment industry id and emoloyment industry name.

Dim_account.csv: Customer account information for who open the account on 2018-03-01, dataset including their branch number, open date, account id, open balance, and customer id.

Fct_Txn_Acct.csv: Spend records between 2018-01-01 and 2018-12-31, inclduing transaction date, account id, customer id, merchant id, category tags, transaction description, spend amount.

Rl_Cust_Seg.csv

Fct_Txn_Cust.csv: Spend records between 2018-01-01 and 2018-12-31, inclduing transaction date, customer id, merchant id, category tags, transaction description, spend amount, year quarter, last quarter and ll quarter.)

## New product development

To successfully launch a new product focused on a specific merchant category for a bank, it is important to carefully consider the type of card that will be offered. Between credit cards and debit cards, credit cards are generally preferred for merchant category-specific products due to the additional benefits and protections they offer, such as purchase protection, extended warranties, and rewards programs. Credit cards also provide consumers with the option to finance their purchases over time, which can be beneficial for more expensive items.

When launching a credit card product, there are four ways in which credit card companies can make a profit: interest on balances, fees, interchange fees from merchants, and rewards programs that incentivize people to use the card more often. These profit avenues will be kept in mind as we explore our transaction data to determine the specific merchant category for the new product.

In order to gain insight into the market and determine the specific merchant category for the new product, we analyzed transaction data from the BusinessCase_Tx.csv dataset, which contains transactions from March 2018 to Octomber 2018. To focus on the merchant category, we filtered the dataset to only include transactions with merchant IDs.

1) The overview of the number of transactions for different categories.

![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/bd561d0a-fdfa-4a2c-81aa-68717dc29364)

We can see that the majority of the transactions are placed for Transfer, Income, Bills and Utilities and Food and Dining from the graph shows above.

2) The overview of the amount of transactions for different categories.
![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/f0f0a84d-aa3b-4bc6-8a52-4a4539ff6c6f)

Based on the total value of transactions for different categories, Income, Transfer, Taxes, Mortgage and Rent, and Bills and Utilities took the leading places in 2018.

3）The total transaction amount and value for transactions with merchant id
![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/9f47e715-464c-4a7b-bf12-7866b7e5e94c)
![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/38d5ef18-d524-4558-ad1b-bc68c5b6351f)

After extracting the transactions that spent on merchants, we can see that Transfer, Taxes, and Bills and Utilities have the highest transaction values respectively, while Bills and Utilities, Food and Dining and Transfer are the categories with highest transaction amount.

4) The transaction amount for different transaction category tags with for merchants in every month

The transactions in March do not have merchant id, so the graphs below will not include the transactions in March.
![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/1cd62e4e-543f-42ba-8905-678daef08eaf)

![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/c3fabf5b-3a95-4162-99e7-027a90421c56)

Based on the graphs above, it is evident that certain merchant categories, such as Transfer, Taxes, Bills and Utilities, and Food and Dining, have the highest transaction amounts in almost every month. This observation is not surprising, as these transactions are necessary for daily living and are therefore frequently made by consumers. However, these categories may not be suitable for the new product, as they will not encourage customers to use the card more often. Instead, we need to focus on other merchant categories that present a potential opportunity for the bank to offer a new product. Additionally, we noted that the 'Fees and Charges' category has 0 value. Therefore, this category will also not be considered for the new product.

By eliminating these categories, we can focus on other merchant categories that may represent a profitable opportunity for the bank. By leveraging transaction data, we can identify these categories and create a product that is tailored to meet the needs and preferences of our target market, while also providing a profitable opportunity for the bank.

After removing the previously mentioned merchant categories, we can obtain a ranking of the total transaction value for each remaining category on a monthly basis. The graphs displaying this information are presented below. By examining these graphs, we can identify any trends or patterns in consumer spending behavior for specific merchant categories over time.

![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/0e6b81fb-d307-4233-9583-8f66c9fb8b7d)
![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/1d49abcc-4af1-4865-9bcb-83ab74093412)

Based on the rank for the total transaction value for each category on each month, we can see that travel takes the leading place for four out of seven months. Even in the months where travel is not the top category, it consistently appears in the top three categories based on total transaction value. This suggests that travel may be the category to focus on for the new product.

Moreover, we investigated the average value per transaction for each category and found that travel has the highest average value per transaction. As one of the main ways for credit card companies to make a profit is through the interchange fee per transaction charged from the merchant, we can see that travel is not only a category that can boost customer consumption but also a profitable category for the bank.
![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/3112ce6d-35f1-4c3c-9213-6a5e0ed3546a)

Based on our analysis of the transaction data, we believe that targeting the travel category for the new product is a promising strategy. With travel being one of the top categories in terms of total transaction value and average value per transaction, it has the potential to not only increase customer consumption but also generate significant profit for the bank through interchange fees charged to merchants.

Furthermore, the fact that only 85 existing customers have used the travel product for the bank suggests that there is a large untapped market for promoting travel credit cards. By understanding the needs and preferences of potential customers in this category and offering tailored benefits and rewards, we can attract new customers and drive revenue growth for the bank.

![image](https://github.com/Xiangzi-Chen/Retail-Banking-Credit-Card-Promotion-Project/assets/90531358/bdd651c5-a2ed-4483-a003-52189bf0d31e)




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


