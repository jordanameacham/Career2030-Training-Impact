# Career2030-Training-Impact
Causal inference analysis of ACME Manufacturing’s Career 2030 training program using Nearest Neighbor Matching (NNM), Propensity Score Matching (PSM), and Inverse Probability of Treatment Weighting (IPTW) to estimate the effect of training on employee promotion likelihood. Includes data preprocessing, modeling, and actionable recommendations.

# Career 2030 Training Program Analysis  

## **Project Overview**  
This project analyzes the **Career 2030** training program at **ACME Manufacturing**, a company with over **60,000 employees**, to assess its impact on **promotion rates and retention**. The dataset consists of **6,000 employee records** and originates from a **randomized controlled trial (RCT)** where **5% of employees were randomly selected for training while another 5% were not**. However, **external managerial influence and self-selection bias** may have affected participation, necessitating **causal inference techniques** to estimate the **true effect of training on promotion**.  

## **Objective**  
As part of an **analytics consulting proof of concept**, this study aims to:  
- **Estimate the causal effect** of training on promotions.  
- **Control for confounding factors** using advanced statistical methods.  
- **Demonstrate the effectiveness of causal inference** in HR analytics.  
- **Provide data-driven recommendations** for program optimization.  

## **Data Description**  
The dataset includes **employee demographics, job-related factors, and training participation data**. Key variables:  

- **Employee Information:** `empid`, `age`, `sex`, `race`, `mstatus`  
- **Job-related Attributes:** `manager`, `raise`, `salary`, `edu`, `vacation`, `disthome`, `testscore`  
- **Training & Promotion Data:** `training`, `promoted`  
- **Benefits & Relationships:** `insurance`, `flexspend`, `retcont`, `hrfriend`, `cxofriend`  

## **Methodology**  
To **mitigate selection bias** and ensure **a reliable estimate of training effectiveness**, we applied **three causal inference techniques**:  

1. **Nearest Neighbor Matching (NNM)** - Matches employees based on pre-treatment characteristics.  
2. **Propensity Score Matching (PSM)** - Estimates training participation likelihood and matches employees accordingly.  
3. **Inverse Probability of Treatment Weighting (IPTW)** - Creates a pseudo-population where training is independent of baseline characteristics.  

We conducted **robustness checks**, including a **Wilcoxon Signed-Rank Test** and **Leave-One-Out Sensitivity Analysis**, to validate findings.  

## **Key Findings**  
- **Baseline regression** showed trained employees were **1.24 times (24%) more likely** to be promoted, but **imbalances required adjustments**.  
- **NNM:** Improved balance but significantly reduced the sample size; estimated a **157% increase in promotion likelihood**.  
- **PSM:** Maintained **1,503 matched pairs**, finding a **134% increase in promotion odds**; a stricter caliper (0.002) confirmed a **157% increase**.  
- **IPTW:** Provided the **most robust estimate**, finding a **287% increase (OR = 3.87, p < 0.001)** in promotion odds while keeping the full sample.  
- **Robustness checks** confirmed findings were **statistically significant and stable**.  

## **Recommendations**  
1. **Improve Data Collection** – Reduce **managerial intervention**, track **employee motivation**, and collect **longitudinal data** on promotions.  
2. **Mitigate Bias in Future Studies** – Implement **stratified randomization**, use **survey-based motivation indicators**, and refine **propensity score weighting techniques**.  
3. **Expand Training Accessibility** – Provide **targeted outreach, flexible schedules, and performance-based incentives** to improve participation.  
4. **Enhance Monitoring** – Develop a **real-time analytics dashboard** to track **training outcomes and refine program design**.  

## **How to Run the Code**  
### **Prerequisites**   
- R and RStudio (for statistical modeling)  
- Required libraries:  
  ```r
  install.packages(c("tidyverse", "Matching", "survey", "tableone", "ggplot2", "glmnet", "caret", "dplyr", "GGally", "moments", "pROC"))

### **Clone the Repository**
```sh
git clone https://github.com/your-username/Career2030-Training-Impact.git
cd Career2030-Training-Impact
```
### **Open RStudio and Load the RMarkdown File**
- Download data file `TrainingPromoData.csv`
- Open `Career 2030 Analysis.Rmd` in RStudio.
- Set working directory to the file where you saved `TrainingPromoData.csv`
- Click "Knit" to generate the full report in HTML/PDF format.

