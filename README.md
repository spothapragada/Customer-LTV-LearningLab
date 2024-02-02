# Customer LTV Analysis

Learning how to perform Customer Lifetime Value (LTV) analysis. Customer LTV is a crucial metric for businesses to understand the long-term value of their customers and make informed decisions about marketing, sales, and customer retention strategies.

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction

In this repository, I explore various techniques and methodologies for calculating and analyzing Customer LTV. I provide code examples, tutorials, and resources to help you understand and implement LTV analysis in your own projects.
Customer LTV Analysis is a useful skill that companies are hiring for and are in demand for consulting projects as well. 

LTV has 3 key factors to the business goals. 

1. How much can we spend to acquire a new customer ? (LTV- CAC - Customer Acquisition Cost)
2. WHich customers are more valuable ? Customer Sergmentation
3. How can we reduce costs to acquire customers ? (CAC)

4 Methods to calculate LTV

### Descriptive 
  - Aggregated Models : Easy but poor
  - Cohort Models : Better but still poor, Using segmentation
### Predictive
  - Probabilistic Models : Better, using regression, intermediate since they are easy to use and interpret and better than descriptive
  - Machine Learning Models : Best, using classification, complex and hard to interpret but best since they are more accurate

### CLV Equation 
  
```mathtex
CLV = (Average Order or Purchase Value * Purchase Frequency) *  Customer Lifespan
```

### Case Study

We will use the transactions of a retail store to create descriptive, predictive and machine learning models to calculate CLV.

We define the terms Churn Customer Lifetime Value (CLV) and Customer Churn as follows:

We define the Lifetime Customer Lifetime Value  as : 

terms to define 
Profit margin : 
   - the profit margin is the percentage of revenue that is profit. For example, if a product costs $100 and the profit margin is 10%, then the profit from the sale of that product is $10. The profit margin is calculated as follows:

Churn rate 
   - what is churn exactly? This can vary in different businesses and contexts. For example, in a subscription-based business, churn could be defined as a customer who has cancelled their subscription. In a retail business, churn could be defined as a customer who has not made a purchase in the last 12 months. In a SaaS business, churn could be defined as a customer who has not logged into their account in the last 30 days. In this case study, we will define churn as a customer who has not made a purchase in the last 12 months.

A quick and dirty descriptive model can aggregate these terms and plug and play into the definitions above. But these can be low accuracy but still directionally instructive. 


Lets looks at some cohort models.

Cohort models are a step up from aggregated models. They are more accurate and can be used to segment customers. One way to do this is split the customers by the start of their first purchase. For example, we can split customers into monthly cohorts based on the month of their first purchase. This will allow us to compare customers who made their first purchase in the same month. We can then calculate the average lifetime value for each cohort. This will give us a better idea of how much revenue we can expect from customers who make their first purchase in a given month.

Moving on to probabilistic models. eg BG/NBD model, Gamma Gamma model, Pareto/NBD model, etc.
While the above models can give a good estimate on average LTV of customers, we might occasionally want insight into individual customers. For example, we might want to know the LTV of a customer who has made 5 purchases in the last 6 months. Or we might want to know the LTV of a customer who has made 10 purchases in the last 12 months. This is where probabilistic models come in. Probabilistic models can be used to predict the LTV of individual customers based on their past behavior. They can also be used to predict the LTV of new customers based on the behavior of similar customers. These then become useful to mmake projections for various time periods.

To do this we must first create a RFM view of the transactional data of the customers. The lifetimes package has useful utilities to do this quickly. Fitting the BG/NBD models to the RFM data will produce plots like Customer Alive Matrix. 

The Gamma-Gamma will give us a predicted average transaction value for each customer. We can then use this to calculate the expected profit from each customer. 

Now that we understand what the CLV is and what its projected to be, we would like to know what factors influence CLV. 
Finally, we will look at machine learning models to help us with this. We will use then shap library to help us understand the factors that influence CLV. Ml Models will also do all the things above like estimating CLV, but also at a customer level predict the probability of spend or churn etc.


Using the regression on predicted CLV, we can then use the shap library to understand the factors that influence CLV.
using the classification on predicted CLV, we can then use the shap library to understand the factors that influence churn. We can translate this into real world actions to reduce churn and increase CLV. 

For the regression model. get the top 20 customers by predicted CLV, take a look at their transaction history and see if there are any patterns. Such as most frequent purchases, most expensive purchases, etc. We can then use this information to create targeted marketing campaigns to increase the CLV of these customers. 


Setting up a DS workflow process can be really useful in creating a repeatable process for CLV analysis.
One of the most valuable steps in the this automation is creating a web application that can sit on top of the 
modeling pipeline. This will allow us to easily share the results of our analysis with other stakeholders in the company. Also allows the stakeholders to interact and test the insights themselves.1


## Installation

We will be using pycaret, lifetimes, shap, xgboost and other libraries. There is an attached yaml file for the environment.

To use the code and resources in this repository, you need to have [Python](https://www.python.org/) installed on your machine. Additionally, you may need to install specific libraries and dependencies, which will be mentioned in the individual code files and tutorials.

## Usage

The code and resources in this repository are organized into different directories based on the specific aspects of Customer LTV analysis. Each directory contains code examples, data files, and documentation to help you understand and apply the concepts.

Feel free to explore the different directories and files to learn more about Customer LTV analysis and how it can benefit your business.

## Contributing

Contributions to this repository are welcome! If you have any suggestions, improvements, or additional resources related to Customer LTV analysis, please feel free to submit a pull request.

## License

This repository is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute the code and resources in this repository for both commercial and non-commercial purposes.
