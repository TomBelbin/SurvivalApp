Shiny App to Study Factors Affecting Survival of Head and Neck Cancer Patients
========================================================
author: Tom Belbin
date: May 22, 2015
transition: rotate

Developing Data Products Course Project

Head and Neck Cancer
========================================================
left: 40%
<br />
<br />
![alt text](Belbin survival-figure/HNcancer.png)
***
<br />
<small>
Facts about Head and Neck Cancer:

- Affects multiple anatomic sites (larynx, oral cavity, oropharynx)
- Associated with tobacco use, alcohol consumption, HPV infection
- Tumors are invasive, can metastasize to regional lymph nodes
- 50,000 diagnoses, 12,000 deaths per year in the US.
- A variety of factors can affect patient survival, including whether or not the tumor has metastasized to regional lymph nodes (positive nodal status).
</small>


========================================================
left: 52%

<small>



```r
hist(patientdata$age,col="Red",
  ylab="Patients", xlab="Age", 
  main="Overview of patient cohort by age at diagnosis")
```

![plot of chunk plot histogram of patient age](Belbin survival-figure/plot histogram of patient age-1.png) 
</small>
***
<br />

<small>
Purpose and Inputs:
- app includes clinical data for 397 head and neck cancer patients as CSV file
- to evaluate survival statistics using either of 3 patient datasets (oropharynx, oral cavity, larynx cancers)
- can choose EITHER death by cancer OR overall death (i.e. other causes) as endpoint for analysis
- can stratify patients according to clinical parameters such as patient gender, patient race, patient ethnicity or patient nodal status and compare survival outcomes.
</small>

Cancer Survival Shiny App
========================================================

Shiny App Outputs:

- all calculations update when inputs are updated (no "Go" or "Submit" button is necessary, no input validation fields necessary)
- output shows summary statistics (number of patients evaluated, median age) for the chosen dataset
- Kaplan Meier (survival) curve shows decrease in the proportion of patients still alive in months following diagnosis for each stratified group (figure legend).
- the significance of the difference in survival by stratification group is calculated using using the G-_rho_ family of tests (Harrington and Fleming, 1982).

Conclusions
========================================================
- using this cohort of 397 patients with head and neck cancer, the Shiny app shows that patient nodal status was the clinical parameter most often associated with patient survival.
- the survival Shiny app can instantly stratify and re-calculate survival statistics and plots without the need of any additional analysis or re-coding.
- this app is easily modifiable for use with other patient datasets, other patient stratifiers, or other survival statistics.
- supporting documentation is available to explain the R code and survival calculations by clicking on the link in the side bar panel of the app.
<br />

<small>
Reference:
Harrington, D. P. and Fleming, T. R. (1982). A class of rank test procedures for censored survival data. _Biometrika_ 69, 553-566.
</small>
