# Bank Customer Churn Analysis (Excel)

An Excel analysis of 9,997 bank customers, built to find out who leaves the bank and why it matters. Of the 9,997 customers, 2,037 exited, an overall churn rate of 20.4%. I cleaned the data in Power Query, created new customer groups through feature engineering, and compared churn across gender, country, age, balance, salary and number of products.

## Dataset

The raw file is not included in this repository because it contains customer identifiers (customer ID and surname). Only the analysis and summary findings are shared here.

Each row is one customer. The columns fall into three groups:

| Group | Columns |
|---|---|
| Customer profile | CustomerId, Surname, Gender, Age, Geography |
| Account and finances | CreditScore, Tenure, Salary, EstimatedSalary, Balance, Just Balance, NumOfProducts, HasCrCard, Card Category |
| Outcome | Exited (1 = left the bank, 0 = stayed) |

Engineered columns I added: Age Group, Tenure Category, Geography Category, Product Category, Balance Category and Salary Category.

## What I did

1. **Cleaned the data in Power Query.** The salary values with the € symbol were stored as text, which made the sort order wrong. I removed the symbol and converted them to numbers. The real salary range is €11.58 to €199,992.48.
2. **Created Age Group.** Customers are aged 18 to 92, so I grouped them into ten-year bands: 18-27, 28-37, 38-47, 48-57, 58-67, 68-77, 78-87 and 88-97.
3. **Created Salary Category.** I split salary into four bands, from Low to Lower-Mid, Mid and High.
4. **Created Balance Category.** I grouped account balances into Low, Medium and High.
5. **Created Product Category.** I turned the number of products into a label: 1 product is a Starter, 2 is an Explorer, 3 is a Connector and 4 is a Champion.
6. **Built PivotTables** to compare churn across each group and calculated churn rates from the stayed and exited counts.

## Key findings

**Customer profile**

| Group | Customers | Share |
|---|---|---|
| Male | 5,456 | 54.6% |
| Female | 4,541 | 45.4% |
| France | 5,013 | 50.1% |
| Germany | 2,508 | 25.1% |
| Spain | 2,476 | 24.8% |

Most customers are aged 28 to 47 (7,267 of 9,997, about 73%).

**Churn by gender**

| Gender | Stayed | Exited | Churn rate |
|---|---|---|---|
| Female | 3,402 | 1,139 | 25.1% |
| Male | 4,558 | 898 | 16.5% |

Women leave at about 1.5 times the rate of men and make up 56% of all customers who exited.

**Churn by country**

| Country | Stayed | Exited | Churn rate |
|---|---|---|---|
| Germany | 1,694 | 814 | 32.5% |
| Spain | 2,063 | 413 | 16.7% |
| France | 4,203 | 810 | 16.2% |

Germany has a quarter of the customers but about 40% of the exits, and its churn rate is twice that of France or Spain.

**Churn by age group**

| Age group | Stayed | Exited | Churn rate |
|---|---|---|---|
| 18-27 | 947 | 73 | 7.2% |
| 28-37 | 3,677 | 389 | 9.6% |
| 38-47 | 2,415 | 786 | 24.6% |
| 48-57 | 472 | 583 | 55.3% |
| 58-67 | 280 | 183 | 39.5% |
| 68-77 | 146 | 22 | 13.1% |
| 78-87 | 20 | 1 | 4.8% |
| 88-97 | 3 | 0 | 0% |

Churn rises sharply from age 38 and peaks at 55.3% for customers aged 48 to 57. The 38-47 and 48-57 groups are 43% of customers but 67% of those who exited. The oldest two groups have too few customers (24 combined) to draw a conclusion.

**Churn by balance**

| Balance category | Stayed | Exited | Churn rate |
|---|---|---|---|
| High | 3,586 | 1,211 | 25.2% |
| Medium | 1,209 | 300 | 19.9% |
| Low | 3,165 | 526 | 14.3% |

High-balance customers are 48% of the bank but about 59% of those who left, so the bank is losing many of its higher-value customers.

**Churn by number of products**

| Product category | Stayed | Exited | Churn rate |
|---|---|---|---|
| Starter (1 product) | 3,672 | 1,409 | 27.7% |
| Explorer (2 products) | 4,242 | 348 | 7.6% |
| Connector (3 products) | 46 | 220 | 82.7% |
| Champion (4 products) | 0 | 60 | 100% |

Explorers have the lowest churn, at 7.6%. Starters, who hold one product, account for 69% of all exits. Almost every customer with three or four products left. These two groups are small (326 customers combined), but the pattern is worth investigating.

**Churn by salary**

| Salary category | Customers | Exited | Churn rate |
|---|---|---|---|
| High | 2,455 | 527 | 21.5% |
| Mid | 2,553 | 517 | 20.3% |
| Lower-Mid | 2,536 | 504 | 19.9% |
| Low | 2,453 | 489 | 19.9% |

Churn stays between 19.9% and 21.5% across every salary band, so salary does not explain who leaves.

## Summary

- Customers most likely to leave are in Germany, aged 38 to 57, female, holding a high balance, or holding one, three or four products.
- Salary has almost no link to churn.
- Customers with two products are the most loyal group.

## Tools

Microsoft Excel (Power Query, feature engineering, PivotTables)

## Author

Rofee'ah Tijani
GitHub: [Rofeeah-Tijani](https://github.com/Rofeeah-Tijani)
