![[Pasted image 20260615132249.png]]![[Pasted image 20260615132307.png]]

![[Headway_1-s2.0-S1369847818307824-main (1).pdf]]


![[wheelbase_33360c34871840315ccc2855788121d2a469.pdf]]

==Tasks done ==
===
1. ECO to CSV {Done}
2. Qu: {Segment video - start to end, & transcribe video using ocr software then user parser script to get output of the ocr tool which is a csv in a structured manner in another csv, merging csv, create S to Y column, then make sure values are consistent using the Target, then check column Q} [Doctor will figure this out and let me know]
3. **Machine Learning **:![[Pasted image 20260616115405.png]] - Goal: Analyse these features and we need to see which one of these features contributes most to the target variable "severity". (Look in too: Why did the model make this sort of a prediction?) [SHAP, Explainable AI]
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