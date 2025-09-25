# Rico Martin Sitorus_Card Behaviour Analysis
This project is technical test for data analyst position at Mandiri Sekuritas. The test done by utilizing the public dataset for debit/credit card usage

**The data retrieved from 3 datasets :**
- **user_data** : contains the information related to user (id, address, age, income, etc).
- **card_data** : contains informations related to cards used in transaction (brand, type, credit_limit, etc).
- **transactions_data** : contains information related to the transactional activites (date, amount, id, user_id, card_id, merchant, etc).

**Database Connection :**
- user_data (id) -> card_data (cliend_id) 
- card_data(id) -> transaction (card_id)

Data queries done via Google Big Query, to obtain the raw data

link to console : https://console.cloud.google.com/bigquery?ws=!1m4!1m3!3m2!1sbehaviouranalysis!2sdata_analysis

<img width="1358" height="673" alt="image" src="https://github.com/user-attachments/assets/02c70c5f-bb12-4db6-8e21-791f11c49771" />

Looker Studio Dashboard : https://lookerstudio.google.com/reporting/d02ddf1b-ce50-431e-b613-c057924c28d5

## DATA QUERIES
The flow to retrieved the data from BigQuery.

**We retrieved raw data, these raw data will be used in further analysis**

**The data will be divided into overview, demographic analysis and demographic behaviour analsysis.**

### Overview
For overview we will check the trended data, transaction frequency, transaction amount in trended. (check the notebook for the code)

### Annual transactions trend (number of transactions vs amounts) based on user's gender
- In this section, we will go deeper up to the demography.
- We'd like to see the trend based on gender.
- What are their respective trend in transaction, spending amount.
- How about their spending per capita
- To obtain this information, we can retrieve the number (frequency of transaction), amount of transaction and number of users that are active, for both gender.

### Transactions type by gender
- After understanding the trend for specific gender.
- In more granular analysis, we will check for the type of purchase usually they prefer.
- Is there any trend (e.g : online transaction) is currently emerging.
- To obtain this, we retrieved raw data that contains the 'use_chip' for each gender.
- We also will check for the spending, and the relation between active user and transaction amount.

### Ages distribution
- After understanding the demography in terms of gender.
- We proceed to see how is the consumer structure based on age distribution.
- Are there particulare age groups that drive mostly the transactions
- To obtain this, we pull the data of age vs transaction.
- We will use this data to plot the distribution and cumulative contribution of ages to total transaction (checking for the pareto)

### Ages_trended
After obtaining the distribution of ages, We found that most of transactions happened mostly driven by productive ages (30s - early 60s)
<img width="895" height="363" alt="image" src="https://github.com/user-attachments/assets/618c0afd-5cd4-48d3-8aef-d105302cfa5a" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/5e7c7064-fee1-49ae-aee2-f6eb1e08a303" />
We will proceed further analysis with the age group (<=30, 31-41, 42-51, 52-61, 62-67, 67+).
We can check for the trended analysis for these age groups.
Hence in this code, we retrieve the number of transactin, amount for each age group in trended

### Age to Debt Ratio
- One of the aspect in financial industry is also the debt and debt-to-income ratio.
- We can observe the trend of the consumer by ages, how's the specific age spend their money/income indicate by this ratio
- To ease the process, we can use the simple analysis by utilizing the average of debt and average of yearly income

### Payment Type trend for each age group
- After understanding the specific group that drive the transaction, and their spending behaviour.
- We now try to check for their transaction preference
- Do specific age group prefer or has increasing trend in certain payment type (e.g : online purchase)
- To achieve this, we check for the trended data of amount, number of transaction, and number of active users (to calculate spend/capita) for each group and payment type (indicated by 'use_chip' column)



