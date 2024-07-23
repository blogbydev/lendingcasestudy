# Lending club case study
> This project is an exploratory data analysis (EDA) on the lending club case study dataset. Lending club is a US based lending platform. Unlike banks, where the loans are provided partly by the investors and partly by the lending platform.
The objective of this case study is to identify possible reasons for loan defaults (a.k.a "Charge Off"). There are various categorical and numerical variables present in the dataset relevant to the entire journey of lending and payments(or recoveries in case of "Charge Off"s). More information describing the dataset can be found in the below sections. Subsequent sections will also show data manipulations, analysis and conclusions.

## Table of Contents
* [Data understanding](#data-understanding)
* [Data cleaning and manipulation](#data-cleaning-and-manipulation)
* [Data analysis](#data-analysis)
* [Observations](#observations)
* [Conclusions](#conclusions)

## Data understanding
- In order to understand the dataset, it's important to understand the lending domain. A very general flow of lending domain can be understood as follows.
A `borrower` requests for a `loan` from the lending platforms/organisations. Based on the `creditprofile` of the `borrower`, the lending platform decides whether to approve or reject the `loan` requests. Furthermore, based on the `creditprofile`, the lending platform also decides on how much of the originally requested loan amount should be funded, what should be the offered interest rate and term of the loan. Once the loan is approved, the `borrower` pays the installments of the loan and a `ledger` is maintained. With time, it becomes evident that the `loan` is fully paid or it turns out to be a defaulter. In case it turns out to be a defaulter, the lending platform reach out to the collection agencies to carry out `recoveries`
- There are various numerical and categorical columns available in the dataset related to `borrower`, `loan`, `creditprofile`, `ledger` and `recoveries`

## Data cleaning and manipulation
- Removal of empty columns (more than 90% missing data)
- Removal of columns with a single value(one value and NaNs)
- Removal of less useful columns for this analysis
    - text columns which require NLP
    - urls with no useful url parts
    - 100% unique values
    - columns related to "recovery" of loan (since these columns will not effect the result whether a member can eventually turn out to be a defaulter)
- Removal of empty rows (more than 50% missing data)
- De-duplication of rows
- Treating missing values
- Derived columns
    - Expanding datetime columns
    - Fixing string columns
## Data analysis
- Segmented Univariate - categorical columns over `loan_status`
- Segmented Univariate - binned numerical columns over `loan_status`
- Bivariate - pairplot for all relevant numerical columns over `loan_status`
- Segmented Bivariate - boxplots for all relevant numerical columns over `loan_status`
- Multivariate - heatmap, mean of numerical columns(after removing outliers) grouped by categorical columns over `loan_status`

## Observations
- Borrowers who live in a rented house are more likely to default as compared to people who own a house
- The borrowers whose annual income was verified default more
- The state of Nevada has proportionally more defaulters
- Borrowers who take long term loans default more
- loan for small businesses tend towards more defaults as compared to other purposes
- The percentage wise charge off as per the grades is as expected
- the assigned sub-grades are mostly matching to their expectations except for "G" sub-grades
- proportionally, the more enquiries that happen on the credit profile in the last 6 months, tend to charge off more
- not a lot of borrowers have publicly recorded derogatory comments, but those who have, are likely to charge off more
- not a lot of borrowers have publicly declared bankruptcies, but those who have are more likely to charge off
- borrowers having less than 30 open accounts have a regular trend of charge offs, and borrowers having more than 30 open accounts are not too many in number, hence no specific action can be taken here
- a lot of last payments happened in the year of 2008 and 2009 due to recession and were declared charged off since they couldn't pay after 2009.
- borrowers having high annual income tend to default less
- the higher the interest rates, the higher the chances of being charged off
- charge off proportion is not correlated to unpaid credit amount
- higher utilization of credit limit shows signs of distress of a weak financial stability, they seem to have defaulted more
- lower payment amounts tend to charge off more
- borrowers whose total payments have been smaller amounts are more likely to default
- there is no clear correlation between the numerical columns, except the expected columns. loan_amnt, funded_amnt, funded_amnt_inv, installment are expected to be highly correlated
- verified borrowers have higher tendency to default if they had high interest rate

## Conclusions
- The process of verification needs to be re-looked at
- Convincing the borrowers to take short term loans may lead to lesser defaults
- loans for small businesses should be scrutinized carefully
- proper scrutinization should be done for borrowers who had frequent enquiries on the credit profile in the last 6 months as that can be a reflection of the borrowers financial statu
- borrowers having publicly recorded derogatory comments should be properly scrutinize
- borrowers who have publicly declared bankruptcies should be scrutinized properly
- events like recession will very likely reflect in a lot of defaults
- borrowers with high annual income are more promising client
- interest rate is an interesting variable that should be analysed with other variables to get an actionable conclusion. Just lowering the interest rates is not feasible
- borrowers having high utilisation of credits should be scrutinized properly
- reduction in payment amount is a sign of tending towards charging of
- borrowers who have done more payments show intent of fully paying the loan