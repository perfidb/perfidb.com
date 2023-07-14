---
layout: base
eleventyExcludeFromCollections: true
---

# Personal Finance Database

PerfiDB is a simple database engineered specifically to store and manage personal finance data. The main features include:

- Using intuitive and elegant SQL-like language to query your transactions
- Full text search in your transaction description
- Intelligently parsing Internet banking statements, it understands the date, amount, and description columns
- A simple yet powerful labelling system, think about Gmail labels for your bank transactions.
- Keeping your sensitive personal finance data locally on your computer

# Examples
```sql
-- Import transactions to account 'amex' from a csv file
IMPORT amex FROM 'bank-exports/2022-03.csv';

-- List all transactions
SELECT * ;

-- List spendings in 2023-02 with amount greater than 100
SELECT * WHERE spending > 100 AND date = 2023-02;

-- Search for transactions with 'Woolworths' in description
SELECT * WHERE description = 'woolworths';

+------+---------+------------+-----------------------------------+--------+--------+
| ID   | Account | Date       | Description                       | Amount | Labels |
+===================================================================================+
| 1936 | cba     | 2018-09-10 | WOOLWORTHS 1166 CHATSWO CHATSWOOD |  32.85 |        |
| 1949 | cba     | 2018-12-14 | WOOLWORTHS 1166 CHATSWO CHATSWOOD |  10.05 |        |
| 3896 | amex    | 2019-02-13 | WOOLWORTHS 1099 ST IVES ST IVES   |  58.05 |        |
| 3521 | amex    | 2019-05-21 | WOOLWORTHS 1099 ST IVES ST IVES   |  41.26 |        |
+------+---------+------------+-----------------------------------+--------+--------+


-- Add two labels (grocery, bread) to all transactions in July containing description text 'bakehouse'
LABEL WHERE date = 2022-07 AND description LIKE 'bakehouse' grocery bread;

-- List all transactions labelled with 'grocery'.
SELECT * WHERE label = 'grocery';
```


# Install


# Contribute
[Github Repo](https://github.com/perfidb/perfidb)
