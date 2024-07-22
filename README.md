# Lending club case study
> This project is an exploratory data analysis (EDA) on the lending club case study dataset. Lending club is a US based lending platform. Unlike banks, where the loans are provided partly by the investors and partly by the lending platform.
The objective of this case study is to identify possible reasons for loan defaults (a.k.a "Charge Off"). There are various categorical and numerical variables present in the dataset relevant to the entire journey of lending and payments(or recoveries in case of "Charge Off"s). More information describing the dataset can be found in the below sections. Subsequent sections will also show data manipulations, analysis and conclusions.

## Table of Contents
* [General Information]()
* [Data understanding]()
* [Data cleaning and manipulation]()
* [Data analysis]()
* [Conclusions]()

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

## Conclusions

## Technologies Used
- matplotlib - version 1.0
- pandas - version 2.0
- seaborn - version 3.0

## Contact
Created by [@blogbydev] - feel free to contact me!