#Analysis of Biomarkers as Indicators of Pancreatic Ductal Adenocarcinoma (PDAC)

# Overview and Problem Statement
Pancreatic ductal adenocarcinoma (PDAC) is an extremely deadly cancer in that once symptoms arise in a patient, it is often already in advanced stages.  With the goal of developing a diagnostic test to screen for PDAC early, researchers have collected data on four urinary biomarkers that have previously been identified to show promise in detecting PDAC.  The four urinary biomarkers are:
*   REG1B:  A protein that may be associated with pancreas regeneration.
*   Creatinine:  A protein that is often used as an indicator of kidney function.
*   LYVE1 (lymphatic vessel endothelial hyaluronan receptor 1):  A protein that may play a role in tumor metastasis.
*   TFF1 (trefoil factor 1):  May be related to regeneration and repair of the urinary tract.

The data can be found on kaggle:
https://www.kaggle.com/johnjdavisiv/urinary-biomarkers-for-pancreatic-cancer

The data was gathered from three patient groups (i.e. independent groups):  healthy patients (control group), patients with non-cancerous pancreatic condition, and patients with PDAC.  Through statistical tests, the analysis researches the question of whether any of these biomarkers are clear indicators of PDAC, and if so, by how much.

# Methods
Three dataframes are created representing the three patient groups: 1 (healthy patients, i.e. control group), 2 (patients with non-cancerous pancreatic condition), 3 (patients with PDAC).

For each of the four biomarkers, statistical tests are run to determine if there is a significant difference between the three groups of patients.  For each of the tests, the null hypothesis (Ho) is that there is no significant difference; whereas, the hypothesis (Ha) is that there is a significant difference. 

Due to nonnormal distributions of the biomarkers within each group, the nonparametric test, Kruskal-Wallis, is used to test for significant difference among the groups, followed by pairwise tests.

# Conclusions and Next Steps
The analysis suggests that the biomarkers, REG1B, LYVE1, and TFF1, are reliable indicators of PDAC. However, there could be potential bias in the data due to patient sex and age sampling.

Group 1(healthy patients, i.e. control group) has a significantly lower number of males, and Group 3(patients with PDAC) has a significantly lower number of females. One way to test for sex bias would be to take a random subset of the males from Group 2 and 3, approximately equal to the number of males in Group 1. Likewise, do the same for Groups 1 and 2 of the females. Then split the data further by male and female (6 total dataframes). Finally, for each biomarker, run statistical male-only and female-only tests between the three diagnoses to see if results are similar to those obtained from the original tests.

The look into age raises the question of whether there was a sampling issue with age or if old age truly does correlate with higher rates of PDAC. That question of age-PDAC correlation is not something that can be answered with this data. Nevertheless, the biomarker study could be protected from potential age bias by resampling the patient population such that all three age distributions are more similar.

Another variable that would be useful to test is the stage, i.e. the cancer stage for the Group 3 patients. For the biomarkers, REG1B and TFF1, Group 3 had many outliers on the high end. Additional tests could check these outliers for a correlation with an advanced stage of PDAC.

Such research could be valuable for biotech companies operating in the oncology space, with the ultimate stakeholder being the general public who will benefit by having early PDAC detection leading to lower fatality rates.
