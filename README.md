# Lending Club Case Study
> Analysis of the Lending data.


## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
### Problem Statement
For our consumer finance company, we need to analyze existing data of past and ongoing loans so that we can devise a Risk Analysis framework to facilitate:-
* Avoiding to give out Loans where probability of default is higher
* Providing Loans where probability of default is lower
* Thus, maximizing growth and lowering risk significantly
### Data used
loan.csv

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions
### Solving Approach
Firstly Cleanup the data to enable analysis
- Create meaningful calculated attributes to help with analysis
- Find patterns where default is higher and lower
- Analyse by Categorical attributes
- Analyse Spread of Numerical attributes
- Analyse correlation of numerical attributes to defaults
- Identify attributes that effect defaults. Some attributes are found before giving loan and some are found during loan lifecycle
- Create a framework for Risk Analysis so that lending Company can
- Avoid bad loans
- Encourage good loans
- Monitor ongoing Loans and raise alerts if risk increases to mitigate risk

### Solution
Create a Customer Scoring mechanism to calculate the score of each customer before deciding on giving the loan or not
- Higher score would mean lower risk
- Higher scores would lead to more Approvals
- Lower scores would lead to more Rejections
- We will also monitor ongoing Loans and the customer during the lifecycle of the loan to Raise Alerts for the Company if a default is going to occur
- For this we will setup alerts for specific attributes occuring

### Scoring
#### Home Ownership
We can give lower score for higher default percentage
- Other are worst & Mortgage are best
- Home Ownership Scores
- Other = 0
- Rent = 1
- Own = 2
- Mortgage = 3

#### Purpose
We can give lower score for higher default percentage
- Small Business is worst and best are credit card, car, major purchase & wedding
- Scoring Purpose
- Small Business = 0
- Renewable Energy = 1
- Educational = 2
- … so on

#### Verification Status
We can give lower score for higher default percentage
- Verified are worst and Not verified are best
- Scoring Verification Status
- Verified = 0
- Source Verified = 1
- Not Verified = 2
- Actually it looks like staff felt the need to verify because the loan seemed risky

#### State
We can give lower score for higher default percentage
- States are listed worst to best
- Scoring State
- We can start giving score for state from 0 for NE and increasing by 1 for eachnext state with lower default percentage
- But keeping the score same for same percentage default ignoring the decimal points

#### Zip Code
Zip codes with loan count higher than 5 & with highest to lowest default rate were extracted
- Scoring zip_code
- Company should assign lower scores for zip codes with higher default
- There are always good and bad localities, those with higher default are bad localities, loans from these localities should get lower scores so that defaults can be avoided

#### Debt to Income Ratio
Left chart is for Non Default while right chart is for Default
- Higher Debt to Income Ratio leads to more default
- If Debt is higher in comparison to
*Scoring dti*
- We can score dti as 100 – dti
- This will lead to higher score for lower dti

#### Inquiries for Loans
Inquiries for Loans in last 6 months is higher for Defaulted Loans as per right chart
- It can be deduced that when a Customer is Inquiring from here and there for Loans that means that he is in financial trouble and Loan Default happens
- This information can be received from the credit bureau
- Scoring – Higher enquiries should have lower score.
- Score = 10 – inquiry count. As number would be less than 10

### Conclusion
At the time of underwriting customer score should be calculated by the software
- A threshold score is to be decided for automatic approvals above that score
- A range of score should be decided below auto approval score for human assisted underwriting, Credit Manager can consider subjective arguments in favor and against approving and decide. Higher loan amounts should be mostly rejected in this range
- Below the above stated lower range all loans should be automatically rejected by the software
- Once Customer Scoring is in place then the Company will have a solid framework for Risk Analysis for underwriting



<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used
* matplotlib.pyplot
* import plotly.express
* import seaborn

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Acknowledgements
- This project was based on upgrad Lending Club Case Study.


## Contact
Created by [@githubusername] - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->