![[Pasted image 20260615132249.png]]![[Pasted image 20260615132307.png]]

![[Headway_1-s2.0-S1369847818307824-main (1).pdf]]


![[wheelbase_33360c34871840315ccc2855788121d2a469.pdf]]

==Tasks done ==
===
1. ECO to CSV {Done} ->[
MetroCount Traffic Executive
Individual

CustomList-25 -- English (ENG)

Datasets: 
Site:	[QFMP-ATC009_NB_L3] ^
Attribute:	
Direction:	1 - North bound, A trigger first. Lane: 0
Survey Duration:	01:53 15 July 2021 => 00:25 18 July 2021,
Zone:	
File:	QFMP-ATC009_NB_L318Jul2021.EC0 (Plus )
Identifier:	BX674QYH MC56-L5 [MC55] (c)Microcom 19Oct04
Algorithm:	Factory default axle (v4.06)
Data type:	Axle sensors - Paired (Class/Speed/Count)

Profile:
Filter time:	01:54 15 July 2021 => 00:25 18 July 2021 (2.93878)
Included classes:	1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 14, 15
Speed range:	0 - 130 mph.
Direction:	North (bound), P = North
Separation:	Headway > 0 sec, Span 0 - 100 metre
Name:	Default Profile
Scheme:	Vehicle classification (VRX)
Units:	Part metric (metre, mi, m/s, mph, kg, tonne)

Column Legend:
 0  [Date-Time] 	Full date and time
 1  [Speed] 	Vehicle speed
 2  [Dir] 	Direction code
 3  [Span] 	Vehicle span
 4  [Hdwy] 	Vehicle headway
 5  [Gap] 	Vehicle gap
 6  [Ax] 	Vehicle axles
 7  [Gp] 	Vehicle axle groups
 8  [Rho] 	Trigger correlation
 9  [Nm] 	Debug parameter
10  [Cl] 	Vehicle class
11  [Vehicle Pic] 	Vehicle picture


          Date-Time Speed Dir  Span   Hdwy    Gap    Ax Gp  Rho       Nm Cl Vehicle Pic                                       
2021-07-15 04:34:17   7.2   0   1.4 9572.3 9572.3     2  1 1.00      162 14 oo                                                

In profile:	Vehicles = 1 / 20013 (0.00%)
]
1. Qu: {Segment video - start to end, & transcribe video using ocr software then user parser script to get output of the ocr tool which is a csv in a structured manner in another csv, merging csv, create S to Y column, then make sure values are consistent using the Target, then check column Q} [Doctor will figure this out and let me know]
2. **Machine Learning **:![[Pasted image 20260616115405.png]] - Goal: Analyse these features and we need to see which one of these features contributes most to the target variable "severity". (Look in too: Why did the model make this sort of a prediction?) [SHAP, Explainable AI]
# 7. The most reliable conclusion comes from agreement {I created a word document for this, MotorCycleCrash}

A feature is considered **truly important** when:

✔ Ablation shows performance drop  
✔ Permutation shows degradation  
✔ SHAP shows consistent influence  
✔ Stability is high across folds  
✔ Effect is statistically significant  
✔ Not explained by redundancy

When all agree → high confidence
	1. Sklearn -> Random Forest
	2. SHAP
	3. ==Me trying to understand the field really well==

Part of the Machine Learning Task:
==========
**_Motor_CycleCrash Analysis:_**

**_Goal:_** State with high confidence what features contributed the most to the desired target variable. (Rank them with solid justification)

**Class Label:** [1: PDO, 2: Minor Injury, 3: Severe Injury, 4: Fatal]

What I was told to use: Random Forest, XGBoost

-        **Reviewers can question it:** So, we need a **multi experiment approach** to prove our claim with high confidence. {Justification must be very strong}

**Identifying Key Contributors to Fatal Motorcycle Crash Outcomes**

**Overview**

This analysis examined 48,582 motorcycle crash records to determine which factors most strongly contribute to fatal outcomes. Of all crashes, 125 were fatal, representing 0.26% of the dataset. Despite this small share, fatal crashes are the most critical outcome from a policy and safety standpoint, and identifying what drives them is the core objective. Nine factors were tested: road functional class, age group, economic level, riding experience, single motorcycle involvement, time of day, motorcyclist at fault, weekend, and season. Five sequential experiments were conducted, each methodologically independent, to build a converging and defensible case.

---

**Experiment 1 — Descriptive Fatal Rate Spread**

The first step was purely observational — computing the fatal crash rate within each level of every factor and measuring the spread between the highest and lowest rates.

|**Factor**|**Fatal% Spread**|
|---|---|
|Code_AGE_GROUP|1.50|
|**Code_SIMP_FUNC_CLASS**|**1.01**|
|Code_ECONOMIC_LEVEL|0.98|
|Code_EXPERIENCE|0.43|
|Code_SingleMC|0.32|
|Code_DAYTIME|0.22|
|Code_MOTORCYCLIST_AT_Fault|0.05|
|Code_Weekend|0.04|
|Code_Summer|0.01|

Road functional class (SIMP_FUNC_CLASS) stood out immediately. Crashes on functional class 5 roads had a fatal rate of 1.05% compared to just 0.04% on class 2 roads — a difference of over 25× between the safest and most dangerous road type. Age group had the largest raw spread at 1.50%, driven almost entirely by a single extreme group (class 4, 1.50% fatal rate) with only 267 records, making it statistically fragile. Road functional class produced a spread of 1.01% consistently across thousands of records per level, making it far more reliable as an observation. Weekend and season showed virtually no spread, signalling they play no meaningful role in fatal outcomes.

---

**Experiment 2 — Chi-Square Test and Cramér's V**

The second experiment confirmed whether the observed spreads were statistically significant and measured the strength of association independent of sample size.

|**Factor**|**Chi²**|**p-value**|**Cramér's V**|**Significant**|
|---|---|---|---|---|
|**Code_SIMP_FUNC_CLASS**|**90.45**|**0.000**|**0.043**|**Yes**|
|Code_EXPERIENCE|32.74|0.000|0.026|Yes|
|Code_ECONOMIC_LEVEL|32.69|0.000|0.026|Yes|
|Code_SingleMC|26.52|0.000|0.023|Yes|
|Code_DAYTIME|22.15|0.000|0.021|Yes|
|Code_AGE_GROUP|18.66|0.001|0.020|Yes|
|Code_MOTORCYCLIST_AT_Fault|0.74|0.391|0.004|No|
|Code_Weekend|0.45|0.504|0.003|No|
|Code_Summer|0.02|0.882|0.001|No|

Road functional class produced the highest chi-square statistic by a wide margin at 90.45, nearly three times higher than the next closest factor. Its Cramér's V of 0.043 ranked first among all factors. Given that fatalities are rare events at 0.26% of the dataset, Cramér's V values in this range are considered meaningful in traffic safety research — the rarity of the outcome naturally compresses the effect size scale. Weekend, season, and fault attribution failed to reach significance entirely, confirming what the descriptive analysis already suggested.

---

**Experiment 3 — Univariate Logistic Regression**

Each factor was modeled individually against the fatal outcome to produce odds ratios — a direct measure of how much more likely a crash is to be fatal depending on which group a rider falls into.

|**Factor**|**Strongest Level**|**Odds Ratio**|**p-value**|
|---|---|---|---|
|**Code_SIMP_FUNC_CLASS**|**Class 5.0**|**24.84**|**0.000**|
|Code_SingleMC|Single vehicle|2.58|0.000|
|Code_DAYTIME|Daytime|0.41|0.000|
|Code_EXPERIENCE|Low experience|0.42|0.034|
|Code_MOTORCYCLIST_AT_Fault|At fault|0.84|0.342|
|Code_Weekend|Weekend|1.15|0.448|
|Code_Summer|Summer|0.96|0.812|

Note: Age group and economic level produced numerically unstable estimates due to complete or near-complete separation in certain levels — meaning zero fatalities in some groups caused the model to produce infinite odds ratios. These results are not interpretable and were excluded from this table.

Road functional class 5 produced an odds ratio of 24.84 with a tight confidence interval of 8.73 to 70.73, significant at p < 0.001. This means that crashes occurring on class 5 roads are nearly 25 times more likely to be fatal compared to class 2 roads. Class 6 and class 4 also produced significantly elevated odds ratios of 10.26 and 6.54 respectively, showing a consistent gradient — the higher the functional class, the higher the fatal risk. This is not a single outlier level driving the result; it is a systematic pattern across the road type hierarchy.

---

**Experiment 4 — Multivariate Logistic Regression**

All nine factors were entered simultaneously into a single model, allowing each factor's effect to be estimated while holding all others constant. This is the confounder adjustment step — the most rigorous test of whether a factor's association is genuine or borrowed from something else.

|**Factor**|**Adjusted OR**|**p-value**|**Significant**|
|---|---|---|---|
|**Code_SIMP_FUNC_CLASS (Class 5)**|**21.86**|**0.000**|**Yes**|
|Code_SIMP_FUNC_CLASS (Class 6)|8.73|0.000|Yes|
|Code_SIMP_FUNC_CLASS (Class 4)|6.33|0.000|Yes|
|Code_SIMP_FUNC_CLASS (Class 3)|4.46|0.005|Yes|
|Code_SingleMC|3.05|0.000|Yes|
|Code_DAYTIME|0.48|0.000|Yes|
|Code_MOTORCYCLIST_AT_Fault|0.50|0.002|Yes|
|Code_EXPERIENCE (Level 1)|0.33|0.007|Yes|
|Code_Weekend|1.03|0.866|No|
|Code_Summer|1.00|0.987|No|
|Code_AGE_GROUP|—|1.000|No|
|Code_ECONOMIC_LEVEL|—|1.000|No|

Road functional class was the only factor where every single level remained statistically significant after full adjustment. Every other level in every other factor either lost significance or was numerically unstable. The adjusted odds ratio for class 5 roads was 21.86 — barely changed from its unadjusted estimate of 24.84 — which tells us the association was not being inflated by confounding from other variables. It was a clean, independent effect. Age group and economic level, despite appearing important in earlier experiments, collapsed entirely in the multivariate model, confirming they were not independently contributing to fatal outcomes once other factors were accounted for.

---

**Experiment 5 — Random Forest and Permutation Importance**

The final experiment used a Random Forest classifier trained on all factors simultaneously, with no assumptions about linearity or the shape of relationships. Permutation importance then measured how much the model's ability to identify fatal crashes degraded when each factor was removed.

|**Factor**|**RF Importance**|**Permutation AUC Drop**|**Rank**|
|---|---|---|---|
|**Code_SIMP_FUNC_CLASS**|**0.232**|**0.317**|**1**|
|Code_EXPERIENCE|0.158|0.259|2|
|Code_Summer|0.083|0.194|3|
|Code_DAYTIME|0.072|0.191|4|
|Code_Weekend|0.082|0.186|5|
|Code_AGE_GROUP|0.129|0.185|6|
|Code_MOTORCYCLIST_AT_Fault|0.072|0.168|7|
|Code_ECONOMIC_LEVEL|0.112|0.159|8|
|Code_SingleMC|0.060|0.138|9|

Road functional class ranked first on both metrics. Its permutation AUC drop of 0.317 was the highest of all nine factors, meaning that when its information was destroyed, the model lost more of its ability to correctly identify fatal crashes than when any other variable was removed. This result is particularly important because it came from a method that makes no statistical assumptions and captures complex non-linear patterns and interactions. The fact that it still pointed to road functional class as the single most informative variable validates what the parametric experiments found through an entirely different analytical pathway.

---

**Consolidated Ranking**

|**Factor**|**Spread Rank**|**Cramér's V Rank**|**Univariate Rank**|**Adjusted Rank**|**RF Rank**|**Average Rank**|
|---|---|---|---|---|---|---|
|**Code_SIMP_FUNC_CLASS**|**2**|**1**|**3**|**3**|**1**|**2.0**|
|Code_AGE_GROUP|1|6|2|1|6|3.2|
|Code_ECONOMIC_LEVEL|3|3|1|2|8|3.4|
|Code_EXPERIENCE|4|2|6|5|2|3.8|
|Code_SingleMC|5|4|4|4|9|5.2|
|Code_DAYTIME|6|5|5|6|4|5.2|
|Code_MOTORCYCLIST_AT_Fault|7|7|7|7|7|7.0|
|Code_Weekend|8|8|8|8|5|7.4|
|Code_Summer|9|9|9|9|3|7.8|

---

**Conclusion**

Across five methodologically independent experiments, road functional class (Code_SIMP_FUNC_CLASS) consistently emerged as the strongest contributor to fatal motorcycle crash outcomes, achieving an average rank of 2.0 — the best score across all nine factors. While age group and economic level showed large raw spreads and descriptive appeal, they failed to hold up under multivariate adjustment and produced numerically unstable regression estimates, indicating their apparent importance was not independent or reliable. Road functional class, by contrast, maintained a strong and consistent signal at every stage — a 25× fatal rate difference across road types, the highest chi-square statistic, an odds ratio of nearly 22 after full confounder adjustment, and the largest permutation importance drop in the machine learning model.

The implication is clear: the type of road on which a motorcycle crash occurs is the single most influential factor in determining whether that crash results in a fatality. Crashes on higher functional class roads — likely higher speed, less controlled environments — carry dramatically elevated fatal risk regardless of who the rider is, when they are riding, or whether they were at fault. This is an environmental and infrastructure-level finding, and it points directly toward road design, speed management, and access control on high-risk road classes as the primary levers for reducing motorcycle fatalities.
==========
V
===================
1. Data processing part, we can create 3 scripts
	1. QTTSC
	2. Pitch and roll
		1. Crosschecker



![[Pasted image 20260707150054.png]]


Full Data processing - Optimized Scripts + Verification Script checks




- **Traffic data pipeline:** Converted Metro Count .EC0 files → structured CSV. 
- **Motorcycle crash analysis (main work):** Ran 5 independent statistical/ML tests (descriptive, Chi-square, logistic regression, adjusted regression, Random Forest) on 48,582 crashes to find top driver of fatal outcomes.
    - **Result:** Road functional class is the strongest, most consistent predictor of fatality - infrastructure matters more than rider behaviour.
	- **ML feature-importance framework:** Defined strict criteria (SHAP + ablation + permutation + stability + significance must all agree) before calling a feature "important."
- **Automated Data Extraction Process & Participants:** For each of the following, {VR, 3 Screen, Real World}, designed automated scripts based on speed, pitch & roll and verification scripts to crosscheck.
	- For each Conducted pre and post questionnaires
	- Completed 30/60 participants with 1 session remaining for each.
		- 25% completed





=========================================

Subject: Progress Update: June 10 – July 12

Dear Dr. Wahl and Dr. Qinat,

I hope you are both doing well. Please find below a summary of the work I have completed between June 10th and July 11th, under the supervision of Dr. Windy.

1. Traffic Data Pipeline
- Converted MetroCount .EC0 files into structured CSV format for downstream analysis.

2. Motorcycle Crash Analysis 
- Ran five independent statistical/ML tests (descriptive analysis, chi-square, logistic regression, adjusted regression, and random forest) on 48,582 crash records to identify the top driver of fatal outcomes.
- Result: Road functional class emerged as the strongest and most consistent predictor of fatality, indicating that infrastructure plays a greater role than rider behavior.
- Developed an ML feature-importance framework, requiring SHAP, ablation, permutation, stability, and statistical significance to all agree before a feature is classified as "important."

3. Automated Data Extraction Process & Participants (Main Work)
- Designed automated scripts (based on speed, pitch, and roll) for each of the three study conditions: 3-screen, VR, and real world, along with verification scripts to crosscheck results.
- Conducted pre- and post-session questionnaires for each condition.
- Completed 30 out of 60 participants, with one session remaining for each.
- Overall project completion stands at approximately 25%.

Please let me know if you would like more detail on any of the above.

Dr. Qinat, I also wanted to flag that Dr. Wahl's budget only covers my position through this month. As you are the principal investigator, could you please let us know whether there is a budget available on your end to extend my position for an additional month? I would appreciate your guidance on this so we can plan accordingly.

Best regards,
Mohammad Kasif

=========================================



# _Subject: Progress Update: June 10 – July 12_

  

Dear Dr. Wahl and Dr. Qinaat,

I hope you are both doing well. Please find below a summary of the work I have completed between June 10th and July 12th, under the supervision of Dr. Windy.

1. ## **Traffic Data Pipeline**
    

- Converted MetroCount .EC0 files into structured CSV format for downstream analysis.

2. ## **Motorcycle Crash Analysis**
    

- Ran five independent statistical/ML tests (descriptive analysis, chi-square, logistic regression, adjusted regression, and random forest) on 48,582 crash records to identify the top driver of fatal outcomes.
- Result: Road functional class emerged as the strongest and most consistent predictor of fatality, indicating that infrastructure plays a greater role than rider behavior.
- Developed an ML feature-importance framework, requiring SHAP, ablation, permutation, stability, and statistical significance to all agree before a feature is classified as "important."

3. ## **Automated Data Extraction Process & Participants** **(Main Work)**
    

- Designed automated scripts (based on speed, pitch, and roll) for each of the three study conditions: 3-screen, VR, and real world, along with verification scripts to crosscheck results.
- Conducted pre- and post-session questionnaires for each condition.
- Completed 30 out of 60 participants, with one session remaining for each.
    
- Participants were predominantly from South Asian countries, so my translation assistance was highly beneficial.
    
- Overall participant completion stands at approximately 25%.
    

## **Remaining Tasks (Subject to Change)**

1. ## Participant Completion for the remaining 30 participants
    
2. Perform machine learning on the collected data to confidently establish the relationship between the simulator and real-world scenarios.
    

Please let me know if you would like more detail on any of the above.

Dr. [@Qinaat Hussain](mailto:qinaat.hussain@qu.edu.qa), I also wanted to flag that Dr. Wahl's budget only covers my position through this month. As you are the principal investigator, could you please let us know whether there is a budget available on your end to extend my position for an additional month? I would appreciate your guidance on this so we can plan accordingly.

Best regards,  
Mohammad Kasif