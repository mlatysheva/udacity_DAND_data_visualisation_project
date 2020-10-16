# Udacity DAND Data Visualisation Project

# Prosper Loan Dataset

## by Maria Latysheva

This project is a part of the Udacity Data Analyst Nanodegree program and focuses on visualisation techniques.

For this project, I analysed a dataset of Prosper loans. Prosper is a peer-to-peer lending platform. Borrowers can find competitive rates for personal loans. Loans are funded by investors, not Prosper itself. The dataset contains 81 parameters and includes, after cleaning, around 77 thousand entries.

The exploratory phase included the following three sections of visualisations:
 
- Univariate visualisations (Borrower Rate, Loan Status, Loan Original Status, Listing Category, Income Range, Debt-to-Income Ratio, Prosper Rating and Prosper Score, Employement Status and Employment Status Duration)
- Bivariate visualisations
- Multivarite visualisations 

### Main features of interest in the dataset

I investigated into the following features and potential interactions between them: 

- How is the Borrower Rate distributed and how is it affected by Loan Amount, Debt-to-Income Ratio, borrower's Prosper Rating?

- What is the specifics of the Prosper loans in terms of the Loan Amount, Loan Status and Debt-to-Income Ratio? 

- How do the loans with the Loan Status of `Defaulted` stand out?


## Summary of Findings

### The unusual points identified and transformations performed

I identified the following unusual points in the distributions:

- **Borrower Rate:** Instead of the expected close to normal distribution, I saw a bimodal distribution plus a very strange peak at 32% (with around 6K entries). A closer look revealed that the 32% rate was mostly offered in 2010 and 2011 for the borroweres with the worst Prosper Rating of `HR`.

- **Loan Status:** The overwelming majority of loans have the status of `Current` or `Completed`. The amount of `Defaulted` and `Past Due` loans was relatively minor. 

- **Original Loan Amount:** The distribution is highly skewed to the right with the peaks being on even numbers (10K, 15K, 20K, 25K) expect for the peak for 4K loans. The overwelming majority of either the entire population or the 4K loans were provided for `Debt Consolidation` listing category to borrowers earning 25K - 75K.

- **Prosper Scores:** The majority of the loans had the average Prosper Rating of C (middle). And the majority of the distribution of Prosper Scores lie in the middle part, being from 4 to 8. 

- **Employment Status Duration:** Most frequently the loans were provided to people who had the fewest years of employment. This is counter to our expectations.

- **Debt-to-Income Ratio:** The disbribution was skewed to the right with some unusual peaks at 0.2, 0.25, 0.37 and 0.43. There were 323 borrowers with the Debt-to-Income Ratio above 1.0 who still obtained loans!

- **Income Range:** The overwelming majority of loans were provided to borrowers earning from 25K to 75K, which is what one would expect.

### Transformations performed

To simplify the analysis or to make the dataset cleaner, I performed the following manipulations with the dataset: 
- Kept only the 18 columns that could be of interest for the analysis

- Kept only entries without missing values

- I extracted the Loan Origination Year from the Loan Origination Date to use in the subsequent analysis

- Recategorised the nominal variables into `category` type: ProsperRating, ProsperScore, ListingCategory and Income Range

- Removed the category 'Not employed' from the Income Range to make subsequent visualisations cleaner. There was only one entry of this category.

- Recategorised all the `Past Due (a paricular number of days)` categories in the Loan Status into a single category `Past Due` to make subsequent visualisations simpler and more to the point.

## Key Insights for Presentation

For the presentation I performed several univariate, bivariate and multivariate visualisations to show the most characteristic features and insights of the dataset, including:

- Univariate: Borrower Rate, Loan Amount, Prosper Score, Income Range and Debt-to-Income Ratio. 

The insights identified here include: the strange peaks in the Borrower Rate distribution, peaks on round numbers in the Loan Amount plus a strange peak at 4K, and several strange peaks in the distribution of the Debt-to-Income Ratio.

- Bivariate: Borrower Rate vs. Loan Amount; and Borrower Rate vs. Prosper Score. 

The insights identified here include: the high Borrower Rates were offered for smaller Loan Amounts, no large amounts were borrowered at high rates; the higher the Prosper Rating is, the lower the Borrower Rate is.


- Multivariate: Borrower Rate above 31% vs. Loan Amount vs. Year; Borrower Rate vs. Debt-to-Income Ratio vs. Loan Amount; and Borrower Rate vs. Loan Amount vs. Prosper Rating. 

The insights identified here include: 

In the subset of Borrower Rates above 31%, there are clusters of rates at particular thresholds (35%, around 34.4%, 33%, above 32%, 32%, around 31.5% and 31%). The majority of these high rates are attributable to 2010 and 2011 years. The high-rate loans all were for amounts below 16K. No loans for an amount larger than 16K have been provided at these high rates. The overwelming majority of the high-rate loans were capped by the amount of 8K.

The overwelming majority of loans were provided to borrowers with the Debt-to-Income Ratio of below 0.4. The overcredited borrowers with DIR above 0.4 are very rare in the dataset. The higher the Debt-to-Income Ratio is, the lower the Loan Amount is. The larger loan amounts were provided at lower interest rates and to borrowers with the Debt-to-Income Ratio under 0.4.

The higher the Prosper Rating of a borrower is, the lower the Borrower Rate is. The Loan Amount increases as the Prosper Rating increases and certain thresholds in the Loan Amount may be observed for particular Prosper Ratings, for example, 10K for the `E`-rating borrowers, 15K for `D`, `C` and `B` borrowers and the largest threshold for `A` and `AA` borrowers. And borrowers with the best Prosper Rating (AA) tend not to borrow large amounts. Way to go to keep their ratings high!
