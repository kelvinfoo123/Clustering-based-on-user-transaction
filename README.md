# Clustering-based-on-user-transaction
## The business question
Given the transaction and user datasets that reflect the cash flow behavior of users, segment the users based on buying patterns.

## About the datasets
The user dataset contains the basic information about the user like id, gender, birthdate.

id: unique ID assigned to the user
created_at: creation date
date_of_birth: user's birthdate
gender: user's gender
country: user's address country
state: user's address state
city: user's address city
The transaction dataset contains the basic information about the user banking transactions like id, account, category, amount.

_id: unique ID assigned to the transaction
user_id: unique ID assigned to the user
account_id: banking account unique id
account_name: banking account name
description: transaction description
type: transaction category (expense, income, transfer)
amount: transaction amount
date: transaction date
extra_fields.category.0: primary transaction category
extra_fields.category.1: secondary transaction category
extra_fields.category.2: tertiary transaction category
extra_fields.merchant_name: merchant name
extra_fields.name: transaction description
extra_fields.payment_channel: payment channel
extra_fields.payment_method: payment method
created_at: creation date
