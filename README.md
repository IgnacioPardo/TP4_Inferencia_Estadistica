# TP4 - Hypothesis Testing in R 📊🔍

## Overview
This repository contains our solution for TP4 of the Statistical Inference course. In this project, we implement and analyze hypothesis tests in R to determine if Provider A's chickens are contaminated (i.e., if their mean arsenic concentration is greater than 80 ppb). The analysis includes formulating the hypothesis test, running simulations, and applying the test to observed data. The final deliverable is an R Markdown report compiled to PDF.

**Team Members:**  
- Ignacio Pardo  
- Luca Mazzarello  

**Date:** October 17, 2022

## Project Description
The main objective is to test whether the average arsenic concentration (µ) in Provider A's chickens exceeds 80 ppb. Our analysis involves:

1. **Formulating the Hypothesis Test:**
   - **Parameter of Interest:** The mean arsenic concentration (µ) in chickens.
   - **Hypotheses:**  
     - Null Hypothesis (H₀): µ = 80  
     - Alternative Hypothesis (H₁): µ > 80  
   - **Test Level:** α = 0.10 (10% risk of wrongly canceling the supplier)
   - **Test Statistic:**  
     \[
     T = \frac{\bar{X} - 80}{\sqrt{16/n}}
     \]
     Under H₀, T follows a standard normal distribution, N(0, 1).
   - **Rejection Region:** Reject H₀ if \( T > 1.281552 \).

2. **Simulation and Analysis:**
   - Generate sample data using a normal distribution \( N(80, 16) \) for a sample size of 5.
   - Compute the test statistic for the sample.
   - Implement a function `estadistico` in R to calculate the test statistic.
   - Run a Monte Carlo simulation (Nrep = 10,000) under H₀ and under H₁ (with µ = 84) to study the distribution of the test statistic.
   - Create density histograms with the standard normal density curve superimposed.
   - Estimate the proportion of samples that reject H₀ and verify if it approximates the significance level.

3. **Real Data Application:**
   - Compute the p-value for an observed sample of arsenic concentrations.
   - Make decisions at significance levels of 0.05 and 0.10 based on the p-value.
   - Propose and implement a simulation to validate the p-value estimate.

## Files and Contents
- **R Markdown Report:**  
  Contains all code, outputs, graphs, and detailed explanations. (Submit as a PDF.)
- **R Script Functions:**  
  - `estadistico`: Function to compute the test statistic.
  - Simulation code for generating 10,000 replications for both H₀ and H₁ scenarios.
- **Data:**  
  - Synthetic data generated using R’s `rnorm` function.
  - Observed sample data for hypothesis testing.

## How to Reproduce the Analysis
1. **Prerequisites:**  
   - R (version ≥ 4.0) and RStudio.
2. **Installation:**  
   Install the required packages:
   ```R
   install.packages(c("rmarkdown", "ggplot2"))
