# Clustering-based-on-user-transaction
## The business question
Given the transaction and user datasets that reflect the cash flow behavior of users, segment the users based on buying patterns.

## About the datasets
The user dataset contains the basic information about the user like id, gender, birthdate.

- id: unique ID assigned to the user
- created_at: creation date
- date_of_birth: user's birthdate
- gender: user's gender
- country: user's address country
- state: user's address state
- city: user's address city

The transaction dataset contains the basic information about the user banking transactions like id, account, category, amount.

- _id: unique ID assigned to the transaction
- user_id: unique ID assigned to the user
- account_id: banking account unique id
- account_name: banking account name
- description: transaction description
- type: transaction category (expense, income, transfer)
- amount: transaction amount
- date: transaction date
- extra_fields.category.0: primary transaction category
- extra_fields.category.1: secondary transaction category
- extra_fields.category.2: tertiary transaction category
- extra_fields.merchant_name: merchant name
- extra_fields.name: transaction description
- extra_fields.payment_channel: payment channel
- extra_fields.payment_method: payment method
- created_at: creation date

## Exploratory Data Analysis 
- 94% of the user records had no gender values. For the remaining 6% of the user records with gender values, 77% of the users were Male and 17% were Female.
- All 803 users were from United States.
- 22% of the users had no state recorded. Among the remaining 78% of the user records with state values, 40% were from California, 14% were from Maryland and 10% were from North Carolina.
- 22% of the user records had no age value since they did not have a recorded date of birth. Among the remaining 78% of the user record, 59% of the users were aged 31-40, 22% of the users were aged 41-60 and 18% of the users were aged 30 and below. Less than 1% of the users were aged above 60.
- All 803 users either created their account 4 or 5 years ago.

- 25% of the transactions were expenses towards food and drink in restaurants. 63% of these transactions were in fast food chains while the remaining 37% were in coffee shops.
- 4% of the transactions were expenses for recreational purposes spent in gyms and fitness centres. Another 4% of the transaction were expenses in sports shops.
- 7% of the transactions were transfer expenses. 57% of these involves debit transfers while the remaining involves deposit.
- 15% were expenses for travel. 74% of these were for taxi services while the remaining were for airline and aviation services.
- 5% of the transactions were income from credit transfer and 6% of the transactions were income from airline and aviation services.
- 6% of the transactions were for credit card payment.
- In terms of number of transactions, majority of the transactions were expenses towards food and drink in restaurants, in particular fast food chains. Travel expenses also covered 15% of the transactions, in particular towards taxi services.

- 56% of the total transaction amount were transfer expenses. 57% of these involves debit transfer and the remaining involves deposit.
- Only 10% of the total transaction amount were expenses towards food and drink in restaurants. 99% of the transaction amount were expenses in fast food chains while the remaining 1% were in coffee shops.
- 6% of the total transaction amount were income from airline and aviation services.
-  4% of the total transaction amount were expenses towards travel. 74% of these were for taxi services and the remaining were for airline and aviation services.
- In terms of amount transacted, majority were for transfer purposes, in particular debit transfer. Only a small percentage of the total transaction amount were expenses towards food and drink (10%) and travel (4%).

- 50% of the transactions occurred in 2021 and 32% of the transactions occured in 2020.
- While the other months account for 4-6% of the transactions each, June accounted for 42% of the transactions. In particular, June 2021 accounted for 38% of the transactions.

## Feature Engineering 
- For each user, we engineered features such as number of expense transaction for travelling using taxi services, number of expense transaction for food and drink in fast food chain, average amount for expense transaction for food and drink in fast food chain, average amount transacted for travelling using taxi services.

## Clustering 
- We compared k-Means clustering, agglomerative clustering and DBSCAN using silhouette score, Davies-Bouldin index and Calinski-Harabasz index. We chose K-Means clustering to cluster the users into 2 clusters.
