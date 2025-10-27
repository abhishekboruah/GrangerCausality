# Establishing The Causal Relationship between Exports and Economic Growth in India

**Colab Link:** [https://colab.research.google.com/drive/1_IOq9QykQv3K36rYwVnPy3EIKQod4CzB?usp=sharing](https://colab.research.google.com/drive/1_IOq9QykQv3K36rYwVnPy3EIKQod4CzB?usp=sharing)

## Overview

This project investigates the causal relationship between India's total exports and its Gross Domestic Product (GDP) using data from 1962 to 2021. The study employs both linear and nonlinear Granger causality tests to determine the direction of causality, if any, between these two crucial economic variables. Understanding this relationship is vital for informed policy-making aimed at improving India's economic growth.

## Table of Contents

- [Colab Link](#colab-link)
- [Introduction](#introduction)
- [Research Question](#research-question)
- [Methodology](#methodology)
- [Empirical Results](#empirical-results)
- [Conclusion](#conclusion)
- [Limitations](#limitations)
- [Scope of Study](#scope-of-study)
- [Bibliography](#bibliography)

## Introduction

Exports play a significant role in a country's economic standing by bringing in foreign funds and contributing to GDP. This study aims to analyze whether improving exports drives economic growth or if economic growth facilitates increased exports in India. India, as a rapidly developing economy, provides an interesting case study for this analysis, the findings of which can help in developing effective policies to boost its growth rate.

## Research Question

What is the causal relationship between Exports and Economic Growth in India, and does a bi-directional causality relation exist between them?

## Methodology

Our methodology involves applying both modern linear and nonlinear Granger causality tests. The use of nonlinear tests is crucial to account for potential structural breaks and nonlinearities in the dynamic relationship between exports and GDP, which standard linear tests might miss.

### Data

The study utilizes Time Series data for export and Real GDP from 1962-2021, extracted from the CMIE database.

### Stationarity

Before applying Granger causality tests, the data's stationarity is assessed using the Augmented Dicky Fuller (ADF) test. If the data is non-stationary (p-value > 0.05), it is transformed into a stationary series using natural logarithm values and differencing techniques.

### Linear Granger Causality Test

This test is a regression model used to determine if one time series helps predict another. We perform the test for up to 4 lags in both directions:
1.  **Do Exports Granger cause GDP?** (Null Hypothesis: Exports do not have a Granger causality with the GDP of India.)
2.  **Does GDP Granger cause Exports?** (Null Hypothesis: The GDP of a country does not have a Granger causality with Exports.)

### Nonlinear Granger Causality Test

Given the limitations of linear tests in capturing complex relationships, we implement the Diks and Panchenko (2006) test. This nonparametric test is more robust in detecting causality by considering feedback effects and other variables that might influence causality. We use an embedding dimension of 5 and a bandwidth (epsilon) greater than 1.5.

## Empirical Results

### Data Overview

Here's a summary of the initial data:
`
`
*Table 1: Initial details of our data.*

| Parameters  | Time    | gdp_val | export  |
| ----------- | ------- | ------- | ------- |
| count       | 60      | 6.00E+01| 6.00E+01|
| mean        | 1991.5  | 4.47E+07| 7.51E+06|
| std         | 17.464249| 4.14E+07| 9.76E+06|
| min         | 1962    | 7.87E+06| 2.55E+05|
| 25%         | 1976.75 | 1.35E+07| 7.68E+05|
| 50%         | 1991.5  | 2.61E+07| 1.76E+06|
| 75%         | 2006.25 | 6.51E+07| 1.36E+07|
| max         | 2021    | 1.48E+08| 3.09E+07|

### GDP vs. Year
`
`
*Figure 1: Graph between GDP of India versus Year.*

### Exports vs. Year
`
`
*Figure 2: Graph between Total Exports of India versus Year.*

### Stationarity Check

The ADF test initially showed the data to be non-stationary (p-value = 0.9987987158). After applying logarithmic transformation and differencing, the data was made stationary.

`
`
*Figure 3: Graph of first-order difference of In(GDP of India) versus Year.*
`
`
*Figure 4: Graph of first-order difference of In(Total Export of India) versus Year.*

### Linear Granger Causality Test Results

For all lag values (1 to 4), the p-values for both directions (Exports to GDP and GDP to Exports) were consistently greater than 0.05. This led us to accept the null hypotheses, indicating that the linear Granger causality test found no significant causal relationship between Exports and GDP in India.

### Nonlinear Granger Causality Test Results

The Diks and Panchenko (2006) nonlinear test revealed a significant unidirectional causality from Exports to GDP.
`
`
*Table 5: p-values for both null hypotheses from Nonlinear Granger Causality Test.*

| Null hypothesis              | T statistics | p-value |
| ---------------------------- | ------------ | ------- |
| Export does not cause GDP    | 2.227        | 0.01296 |
| GDP does not cause Export    | -0.836       | 0.79843 |

With a p-value of 0.01296 (less than 0.05), we reject the null hypothesis that Export does not cause GDP. Conversely, with a p-value of 0.79843 (greater than 0.05), we fail to reject the null hypothesis that GDP does not cause Export.

## Conclusion

The linear Granger causality test did not establish any causal relationship between India's GDP and Exports. However, the more robust nonlinear Granger causality test (Diks and Panchenko, 2006) revealed a **unidirectional causality from Exports to GDP**, but not vice versa. This suggests that for a non-oil GDP country like India, focusing on enhancing export capabilities can directly influence its economic development. Causal research like this is crucial for understanding how current actions can shape future economic outcomes.

## Limitations

1.  **Stationarity Requirement:** Granger causality tests necessitate stationary data.
2.  **Linear Test Inconclusiveness:** The linear Granger causality test did not yield a significant relationship.
3.  **Linear Test Limitations:** Standard linear Granger causality tests may lead to misleading conclusions as they do not account for structural breaks or nonlinearities.
4.  **Nonlinear Test Sample Size:** The Diks and Panchenko test may under-reject in samples smaller than 500 observations. Our sample size of 60 observations might potentially affect the results, suggesting the need for further investigations with larger datasets.

## Scope of Study

Future research could incorporate more variables into a multivariate regression analysis to establish Granger relationships (e.g., unemployment index, literacy rate). Nonlinear tests, by accounting for feedback effects and other influencing variables, offer a more comprehensive understanding of the causal link between exports and GDP.

## Bibliography

*   Amiri, A., & Gerdtham, U. G. (2012). Granger causality between exports, imports, and GDP in France: Evidence from using geostatistical models. Economic Research Guardian, 2(1), 43-59. [Link](https://ideas.repec.org/a/wei/journl/v2y2012i1p43-59.html)
*   Mehrara, M., & Firouzjaee, B. A. (2011). Granger causality relationship between export growth and GDP growth in developing countries: A panel cointegration approach. International Journal of Humanities and Social Science, 1(16), 223-231. [Link](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.1056.9891&rep=rep1&type=pdf)
*   Ajmi, A. N., Aye, G. C., Balcilar, M. & Gupta, R.(2013). Causality between Exports and Economic Growth in South Africa: Evidence from Linear and Nonlinear Tests. [Link](https://ideas.repec.org/p/pre/wpaper/201339.html)