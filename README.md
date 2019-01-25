# Infer-FOMC-rates-decision-using-ANFIS

## Preamble

Many Machine Learning techniques, especially Deep ML, are very good to classify/recognize data petterns, their limited interpretibility is a ney weakness in creating Expert Systems. It is highly desirable in such systems to know what rules are being used in order to know what rules need to be added. The rules are implemenetd not only to match historical data, but to set policies, including special ones like safety, conservatism, legal etc. This project is an example in such direction.

## Domain Background

The federal funds rate is the interest rate at which depository institutions lend balances at the Federal Reserve (FED) to other depository institutions overnight. Changes in the federal funds rate trigger a chain of events that affect other short-term interest rates, foreign exchange rates, long-term interest rates, the amount of money and credit, and, ultimately, a range of economic variables, including employment, output, and prices of goods and services 1. This is one of the tools available to the FED to influence the availability and cost of money and credit to help promote national economic goals. The FED is supposed to arrive at interest rate decisions after considering many financial economic data and models. The decision is usually made with voting at quarterly FOMC (Federal Open Market Committee) meetings. Emergency decisions are rare but possible, which happened in 2008-2009 financial crisis.
https://www.federalreserve.gov/monetarypolicy/fomc.htm

## Problem Statement

Despite its paramount importance, it is not clear how these decisions are made. Voting members subjectivities may also play a role. The ‘Taylor’ rule2 is a conceptual of how interest rates should be, given unemployment and inflation. Output from Taylor rule, however, does not adequately reflect the FED’s decision: https://en.wikipedia.org/wiki/Taylor_rule.

Having rules closer to actual FED rates would be helpful. Furthermore, financial models have limited interpretation on the decision process. I propose using Adaptive fuzzy inference neural network as an alternative approach. Observable FED rates decision is modeled by changes in effective FED fund rates. Input data include common cited series, such as Inflation CPI/Income-change, Unemployment rate, GDP and SP500. Fuzzy logic membership functions will be Gaussian-shape.

## Datasets and Inputs

FED target rates since 1990:
http://www.fedprimerate.com/fedfundsrate/federal_funds_rate_history.htm

Fed Funds Rate History with Its Highs, Lows and Chart:
https://www.thebalance.com/fed-funds-rate-history-highs-lows-3306135

FRED effective FED Funds Rate:
https://fred.stlouisfed.org/series/FEDFUNDS

NY FED Federal Funds Data:
https://apps.newyorkfed.org/markets/autorates/fed%20funds

## Solution Statement

Use Mamdani-Type Fuzzy Logic with ANFIS on historical data to extract FOMC interest rates decisions. The model helps answering the following questions:
1. Is there a general set of rules closely represent FOMC rates decision?
2. Are the rules stable across regime-change periods in history?
3. What would FED rates be when applying changes to those rules?

## Benchmark models

A Fuzzy Decision Tree will be used as benchmark model. This model is based on changes in Entropy, thus is conceptually distinctive from the main model.

## Evaluation Metrics

- Comparison with historical data
- Quality of extracted rules, number of rules
- Differentiation between different sets of rules

## Project Design:

- Clean up relative changes in Fed effective/target rates and mimic FOMC decisions.
- Collect FOMC input variables: Core PCI/Employment/Wage/SP500 return.
- Use Gaussian mixture to create Fuzzy membership Functions.
- Extract rules from data using ANFIS.
- Create Fuzzy Decision Tree benchmark model.
- De-fuzzification (generate actual crisp values) and compare with historical


