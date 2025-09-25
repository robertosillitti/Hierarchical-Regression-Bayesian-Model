# Hierarchical-Regression-Bayesian-Model
This project investigates the factors that may influence the rate of post-operative complications following cholecystectomy procedures in Italian healthcare facilities. I applied a Bayesian hierarchical regression model to assess the impact of hospital characteristics and regional differences on surgical outcomes.

## Dataset Description
The dataset contains information on the **30-day post-operative complication rate** for cholecystectomy procedures performed in various healthcare facilities across Italy.  

- **Observations:** 336 hospitals and accredited private clinics  
- **Geographic scope:** Italian regions (except Aosta Valley and Molise)   
- **Source:** [PNE – National Outcomes Program](https://pne.agenas.it/)  

### Covariates included in the model
| Covariate                        | Description                                                                 |
|----------------------------------|-----------------------------------------------------------------------------|
| Length of stay < 3 days          | Adjusted percentage of patients discharged within 3 days (performance indicator) |
| N. interventions                 | Total number of cholecystectomy procedures performed in each facility       |
| Emergency Room                   | Whether the facility has an emergency department                            |
| Healthcare facility category     | Categorical: University hospital/IRCCS, Private clinic, Public hospital     |

---

## Goal of the Analysis
- Evaluate whether the selected covariates affect the rate of post-operative complications.  
- Investigate regional disparities in outcomes and identify whether some regions perform better than others.  
- Leverage a Bayesian hierarchical model to borrow strength across groups, improving estimates where data are sparse.  

This analysis focuses on cholecystectomy as a common and representative procedure to assess hospital performance.  
The same methodology could be extended to other procedures with high incidence or clinical relevance (e.g., hip fracture surgery in patients over 65).  
The Bayesian approach can provide more stable and informative estimates than frequentist models, especially when regional sample sizes are small, and it allows for partial pooling, improving inference across regions.  

---

## Methodology
This project workflow include:

1. Data cleaning and selection of relevant predictors
2. Model specification 
3. Implementation of the Gibbs Sampling algorithm
4. Convergence diagnostics and interpretation of the results with posterior predictive checks

To estimate the model parameters, I implemented a Gibbs sampling algorithm, a Markov Chain Monte Carlo (MCMC) algorithm that iteratively samples from the full conditional distributions of each parameter. It is particularly suitable in Bayesian settings, where closed-form solutions are often unavailable.

---

### Requirements
Packages: `openxlsx`,`dplyr`,`coda`,`gridExtra`,`MASS`,`Matrix`,`knitr`,`ggplot2`,`bayesplot`,`tidyr`


