**

# What your paper can look like

Think of your paper as 4 layers:

1. Data problem (literature is messy)  
      
    
2. Your solution (extraction + curation + grounding)  
      
    
3. What you built (dataset + schema + QC)  
      
    
4. What it enables (trends + ML + physics-informed ML)  
      
    

That way, even if the ML is weak (common in sparse materials data), the paper is still strong.

---

# A strong paper structure you can use now

## Title (placeholder styles)

Pick later, but here are directions:

- Evidence-grounded literature dataset for thermoelectric polymers enabling materials informatics analysis of zT  
      
    
- From literature to learning: a curated thermoelectric polymer database for trend discovery and zT modeling  
      
    
- A data curation and extraction pipeline for thermoelectric polymer performance and processing parameters  
      
    

---

## Abstract (what it will contain)

Your abstract will likely have these 5 pieces:

- Problem: thermoelectric polymer data is scattered and inconsistent  
      
    
- Method: evidence-grounded extraction + curation pipeline  
      
    
- Output: structured dataset with composition, processing, and performance variables  
      
    
- Analysis: trend analysis + baseline ML / physics-informed ML  
      
    
- Contribution: enables reproducible and interpretable zT-related studies  
      
    

---

## 1. Introduction

### What to say

- Why thermoelectric polymers matter (flexible/low-cost/energy harvesting context)  
      
    
- Why optimizing zT is difficult (multi-variable tradeoffs)  
      
    
- Why literature-based data is hard (different units, conditions, reporting styles, missing values)  
      
    
- Why materials informatics is promising  
      
    
- The gap: lack of a high-quality, evidence-grounded curated dataset/pipeline  
      
    
- Your contribution summary (dataset + extraction + validation + trends + ML readiness)  
      
    

### Your contribution is already visible here

Even before modeling, you can claim:

- A structured representation of thermoelectric polymer experiments  
      
    
- A reproducible extraction and curation workflow  
      
    

---

## 2. Related Work

### Subsections

- Thermoelectric polymer experimental literature  
      
    
- Materials informatics for functional materials  
      
    
- Scientific IE / NLP for materials literature  
      
    
- Existing polymer/thermoelectric datasets (if any)  
      
    
- Physics-informed ML in materials  
      
    

### Your contribution angle here

You are positioning your work as a bridge between:

- experimental literature and  
      
    
- usable ML-ready data  
      
    

That bridge itself is publishable.

---

## 3. Problem Definition and Scope (super important)

This section prevents confusion and makes your paper look mature.

### Define the unit of analysis (row definition)

Example (recommended):

One row corresponds to one polymer formulation under a specific processing condition and measurement temperature.

This is huge. It makes everything else cleaner.

### Define targets

- Primary target: zT  
      
    
- Secondary targets: Seebeck coefficient, electrical conductivity, thermal conductivity, power factor  
      
    
- Auxiliary targets: extraction confidence, evidence grounding validity, missingness indicators  
      
    

### Define scope

- Included literature types  
      
    
- Included polymer systems  
      
    
- Temperature conditions  
      
    
- Reported vs derived variables  
      
    
- Exclusions (unclear measurement conditions, insufficient metadata, etc.)  
      
    

### Possible contribution here

- A clear problem formalization for thermoelectric polymer informatics (often missing in early studies)  
      
    

---

## 4. Data Schema and Parameter Taxonomy

This is one of your strongest contribution sections.

### What this section contains

A full data dictionary grouped into categories such as:

#### A. Material identity

- Polymer name  
      
    
- Polymer family/class  
      
    
- Dopant identity  
      
    
- Dopant class  
      
    
- Composite/filler presence  
      
    
- Additives  
      
    

#### B. Composition and formulation

- Doping level  
      
    
- Solvent  
      
    
- Solvent ratio  
      
    
- Concentration  
      
    
- Mixing conditions  
      
    
- Monomer structure (if relevant)  
      
    
- Molecular weight (if available)  
      
    

#### C. Processing conditions

- Film preparation method  
      
    
- Coating method  
      
    
- Drying conditions  
      
    
- Annealing temperature/time  
      
    
- Post-treatment  
      
    
- Stretching/orientation treatment  
      
    

#### D. Geometry and morphology

- Thickness  
      
    
- Porosity  
      
    
- Crystallinity (if reported)  
      
    
- Surface/microstructure descriptors (optional text tags)  
      
    

#### E. Measurement conditions

- Measurement temperature  
      
    
- Atmosphere/humidity  
      
    
- Direction (in-plane / through-plane)  
      
    
- Instrument/method notes (if available)  
      
    

#### F. Performance outcomes

- Seebeck coefficient (S)  
      
    
- Electrical conductivity (sigma)  
      
    
- Thermal conductivity (kappa)  
      
    
- Power factor (PF)  
      
    
- zT  
      
    

#### G. Provenance and quality

- DOI  
      
    
- Year  
      
    
- Evidence location (table/text/figure/page)  
      
    
- Extraction method  
      
    
- Confidence score  
      
    
- Verification status  
      
    
- Notes/ambiguity flags  
      
    

### Possible contributions here

- A standardized schema for thermoelectric polymer literature  
      
    
- A parameter taxonomy linking process/composition/measurement/performance  
      
    
- A reusable template for future datasets  
      
    

This alone is a real contribution.

---

## 5. Literature Collection and Inclusion Criteria

### What goes here

- Search strategy (databases/keywords)  
      
    
- Time range  
      
    
- Inclusion criteria  
      
    
- Exclusion criteria  
      
    
- Screening workflow (title/abstract/full-text)  
      
    
- Number of papers screened/included (PRISMA-style flow if possible)  
      
    

### Possible contributions

- A transparent reproducible dataset assembly protocol  
      
    
- A benchmark literature coverage snapshot for the field  
      
    

---

## 6. Extraction and Grounding Pipeline

This is a major methods contribution.

### What to include

- PDF text extraction  
      
    
- Table extraction  
      
    
- Figure/text parsing strategy (if used)  
      
    
- Rule-based logic (regex)  
      
    
- spaCy/NLP pipeline  
      
    
- Entity normalization (names/synonyms)  
      
    
- Unit normalization  
      
    
- Evidence grounding (you already do this very well)  
      
    
- Confidence scoring  
      
    
- Manual verification loop  
      
    
- Error categories and correction strategy  
      
    

### Very strong contributions here

You may be contributing:

1. Evidence-grounded extraction framework  
    (not just extracted value, but where it came from)  
      
    
2. Hybrid extraction method  
    (rules + NLP + validation logic)  
      
    
3. Normalization pipeline  
    (units/synonyms/experimental condition standardization)  
      
    
4. Error-aware curation workflow  
    (especially for critical variables like doping level)  
      
    
5. Human-in-the-loop validation design  
    (important for publication quality)  
      
    

If your extraction is robust, this can become one of the main paper contributions.

---

## 7. Quality Control and Dataset Reliability

Many papers skip this. If you include it, your paper becomes stronger.

### What to report

- Inter-annotator agreement (if available)  
      
    
- Manual audit on sample subset  
      
    
- Precision/recall (for extracted fields, if you can estimate)  
      
    
- Coverage rate by field  
      
    
- Missingness patterns  
      
    
- Unit conversion consistency checks  
      
    
- Constraint checks (e.g., PF consistency with S and sigma if units allow)  
      
    
- Duplicate detection across papers/records  
      
    
- Ambiguity flags  
      
    

### Possible contributions

- A quality assurance protocol for literature-derived materials datasets  
      
    
- Quantification of data reliability and uncertainty  
      
    
- A framework for deciding which rows are “ML-ready”  
      
    

This is very publishable and often underappreciated.

---

## 8. Dataset Characterization and Exploratory Analysis

This is your first result section and is almost guaranteed to produce publishable content.

### What to include

- Number of papers, records, unique polymers, dopants  
      
    
- Year-wise growth of literature  
      
    
- Most common polymer-dopant systems  
      
    
- Distribution of measurement temperatures  
      
    
- Performance metric availability (zT vs PF vs S vs sigma vs kappa)  
      
    
- Missingness heatmap  
      
    
- Range/distributions of key parameters  
      
    
- Co-reporting patterns (which variables tend to appear together)  
      
    
- Correlation analysis (carefully, with caveats)  
      
    
- Clusters of formulations/processing routes  
      
    

### Possible contributions

- First broad data-driven map of thermoelectric polymer literature structure  
      
    
- Identification of reporting gaps/biases  
      
    
- Discovery of data availability bottlenecks for zT modeling  
      
    

Even if you do no advanced ML, this can still be a strong paper.

---

## 9. Downstream Modeling and Physics-informed Analysis (adaptive section)

This section changes depending on data quality. That is okay.

### Path A (if zT data is enough)

- Baseline ML prediction of zT  
      
    
- Cross-validation  
      
    
- Feature importance / interpretable model  
      
    
- Uncertainty estimates  
      
    
- Error analysis by polymer class or temperature range  
      
    

### Path B (if zT is sparse)

Use secondary targets:

- Predict PF or sigma or S  
      
    
- Multi-task learning on available properties  
      
    
- Impute missing properties carefully (if justified)  
      
    
- Use zT only for subset evaluation  
      
    

### Path C (physics-informed / consistency-aware)

Examples of contributions:

- Physical consistency constraints between S, sigma, PF  
      
    
- Temperature-aware modeling  
      
    
- Unit-aware checks  
      
    
- Feature transformations motivated by thermoelectric physics  
      
    
- Filtering nonphysical outliers  
      
    

### Possible contributions here

- Baseline benchmark for literature-derived thermoelectric polymer prediction  
      
    
- Physics-aware data filtering/modeling strategy  
      
    
- Interpretable process-structure-property trend analysis  
      
    

Important: if performance is not amazing, you can still contribute by showing why (data sparsity, condition heterogeneity, reporting inconsistency).

That is a valid scientific result.

---

## 10. Discussion

### What to discuss

- Which variables appear most influential (with caution)  
      
    
- Confounders (temperature, measurement direction, lab-specific methods)  
      
    
- Literature reporting inconsistency as a scientific bottleneck  
      
    
- What current data supports vs does not support  
      
    
- How future papers should report data for better ML use  
      
    

### Powerful contribution here

You can propose a reporting checklist for thermoelectric polymer papers.

That is an excellent publication contribution.

---

## 11. Limitations

This increases credibility.

Mention things like:

- Literature bias toward high-performing systems  
      
    
- Sparse thermal conductivity reporting  
      
    
- Inconsistent measurement protocols  
      
    
- Extraction ambiguity from figures/text  
      
    
- Small data size for certain polymer families  
      
    
- Nonuniform temperature conditions  
      
    

This does not weaken your paper. It makes it trustworthy.

---

## 12. Conclusion and Future Work

End with:

- What dataset/pipeline you built  
      
    
- What trends you observed  
      
    
- What the field can now do with this dataset  
      
    
- Next steps (active learning, inverse design, better standardized reporting, multimodal extraction)  
      
    

---

# All possible ways you are contributing something (big list)

Here is the main thing you asked for.  
You are not only contributing “an ML model”.

You may be contributing in multiple contribution classes at once.

---

## A. Data contribution (very strong and common)

You contribute by creating something the field does not have in usable form.

### Examples

- A curated dataset of thermoelectric polymer parameters  
      
    
- A structured representation of process-structure-property-performance relationships  
      
    
- A zT-centered dataset with secondary outcomes (PF, S, sigma, kappa)  
      
    
- A measurement-condition-aware dataset (temperature, direction, etc.)  
      
    
- A machine-readable benchmark dataset from scattered literature  
      
    

### Publishable claim examples

- “We present the first evidence-grounded literature-derived dataset for thermoelectric polymer informatics”  
      
    
- “We standardize heterogeneous experimental reports into an ML-ready schema”  
      
    

---

## B. Methodology contribution (extraction + curation pipeline)

You contribute the method used to build reliable data.

### Examples

- Hybrid extraction pipeline (regex + NLP + rule validation)  
      
    
- Evidence-grounded extraction with traceability  
      
    
- Confidence scoring per extracted field  
      
    
- Human-in-the-loop correction workflow  
      
    
- Unit and synonym normalization system  
      
    
- Error-aware extraction for critical parameters like doping level  
      
    

### Publishable claim examples

- “We propose a traceable extraction pipeline that links each value to source evidence”  
      
    
- “We introduce a curation workflow that improves reliability of literature-derived polymer parameters”  
      
    

---

## C. Benchmark contribution

You contribute a baseline that future work can compare to.

### Examples

- Baseline extraction performance (precision/recall on annotated subset)  
      
    
- Baseline ML models for zT/PF prediction  
      
    
- Benchmark split strategy (random vs polymer-family split vs time split)  
      
    
- Benchmark missingness-aware modeling setup  
      
    
- Benchmark evaluation protocol for literature-derived materials data  
      
    

### Publishable claim examples

- “We establish the first baseline prediction benchmarks on curated thermoelectric polymer literature data”  
      
    

---

## D. Scientific insight contribution (trend discovery)

You contribute new understanding, not just data.

### Examples

- Which variables are most associated with high PF or zT  
      
    
- Common high-performing polymer-dopant-processing combinations  
      
    
- How annealing / thickness / doping level trends behave  
      
    
- Reporting biases that distort perceived trends  
      
    
- Performance tradeoffs (e.g., conductivity vs Seebeck tendencies under certain conditions)  
      
    

### Publishable claim examples

- “Data-driven analysis reveals key process/composition trends associated with reported thermoelectric performance”  
      
    

---

## E. Quality / reproducibility contribution

Huge for publishable work.

### Examples

- Evidence-grounding framework  
      
    
- Auditability of extracted values  
      
    
- Reproducibility checklist for dataset generation  
      
    
- Confidence and ambiguity labels  
      
    
- Data provenance design (DOI, page, table/figure location)  
      
    

### Publishable claim examples

- “We prioritize reproducibility through evidence-linked records and explicit uncertainty tracking”  
      
    

---

## F. Standardization contribution (field-building)

You contribute a common language/format for the field.

### Examples

- Parameter taxonomy for thermoelectric polymers  
      
    
- Controlled vocabulary for dopants, processing methods, measurement conditions  
      
    
- Recommended metadata standards for reporting TE polymer experiments  
      
    
- Suggested minimum reporting template for ML-ready publications  
      
    

### Publishable claim examples

- “We propose a practical reporting and schema standard to improve interoperability across thermoelectric polymer studies”  
      
    

This can be very impactful.

---

## G. Physics-informed ML contribution (if data supports it)

This is the advanced layer.

### Examples

- Physically consistent feature engineering  
      
    
- Constraints using known relationships (PF, zT components)  
      
    
- Temperature-aware modeling  
      
    
- Outlier filtering based on thermodynamic/measurement plausibility  
      
    
- Hybrid mechanistic + data-driven trend analysis  
      
    

### Publishable claim examples

- “We demonstrate a physics-informed modeling strategy for noisy, literature-derived thermoelectric polymer datasets”  
      
    

---

## H. Negative-result / feasibility contribution (also valid)

If zT prediction is weak, that can still be a contribution if analyzed correctly.

### Examples

- zT prediction not reliable due to sparse/heterogeneous kappa reporting  
      
    
- Stronger performance for PF than zT due to data completeness  
      
    
- Modeling sensitive to missingness and measurement-condition variation  
      
    
- Need for standardized reporting to unlock robust ML  
      
    

### Publishable claim examples

- “We show that data heterogeneity, rather than model complexity, is the primary bottleneck for zT prediction from current literature”  
      
    

That is a real and useful result.

---

# How the paper changes depending on what happens later

You said you do not know the outcome yet. Good. Build a paper that can branch.

## Scenario 1: Data is great, modeling works

Paper emphasis:

- dataset + extraction + modeling + insights  
      
    

## Scenario 2: Data is moderate, modeling is weak

Paper emphasis:

- dataset + extraction + quality analysis + trend insights + benchmark limitations  
      
    

## Scenario 3: zT too sparse

Paper emphasis:

- dataset + extraction + secondary target modeling (PF/S/sigma) + reporting gap analysis  
      
    

## Scenario 4: Extraction pipeline is the strongest part

Paper emphasis:

- methodology paper with dataset release and validation + early case study trends  
      
    

All four are valid papers.

---

# A practical contribution statement you can use in your paper

You can use this style (adapt later):

### Example contribution bullets

- We develop an evidence-grounded extraction and curation pipeline for thermoelectric polymer literature, linking extracted values to source evidence locations for auditability.  
      
    
- We define a standardized schema capturing composition, processing, measurement conditions, and performance metrics relevant to zT-centered analysis.  
      
    
- We construct a literature-derived dataset suitable for downstream trend analysis and ML/physics-informed ML tasks.  
      
    
- We quantify data quality, coverage, and missingness patterns, highlighting current bottlenecks for reliable zT prediction.  
      
    
- We provide baseline data-driven analyses (and, where feasible, predictive models) to identify promising variables and design directions.  
      
    

This is strong even before final results.

---

# What figures/tables your paper will likely have (helps you visualize the final paper)

## Likely figures

1. Pipeline diagram (paper -> extraction -> normalization -> grounding -> QC -> dataset -> ML)  
      
    
2. PRISMA/search flowchart (papers screened/included)  
      
    
3. Schema/taxonomy diagram (parameter groups)  
      
    
4. Coverage bar chart (how often each parameter is reported)  
      
    
5. Missingness heatmap  
      
    
6. Distribution plots (temperature, sigma, S, PF, zT)  
      
    
7. Polymer-dopant frequency chart  
      
    
8. Trend plots (e.g., PF vs doping level, stratified by temperature if possible)  
      
    
9. Model performance chart (if ML done)  
      
    
10. Feature importance / SHAP-like interpretability plot (if applicable)  
      
    

## Likely tables

1. Dataset schema / data dictionary (core fields)  
      
    
2. Inclusion/exclusion criteria  
      
    
3. Unit normalization rules  
      
    
4. Extraction performance / validation results  
      
    
5. Baseline model results  
      
    
6. Error analysis / failure modes  
      
    

Just seeing this list helps make the project feel real and structured.

---

# How to avoid the biggest mistake now

Do not define your paper as:

- “We will predict the best polymer with ML.”  
      
    

That is too narrow and risky.

Define it as:

- “We build a reliable, evidence-grounded thermoelectric polymer dataset and demonstrate its use for trend analysis and ML/physics-informed ML toward zT-related performance understanding.”  
      
    

That survives uncertainty.

---

# A simple paper blueprint you can start writing today

Start a document with these headings now and fill as you go:

- Introduction  
      
    
- Related Work  
      
    
- Problem Definition and Scope  
      
    
- Data Schema and Parameter Taxonomy  
      
    
- Literature Collection and Screening  
      
    
- Extraction and Grounding Pipeline  
      
    
- Data Curation and Quality Control  
      
    
- Dataset Characterization  
      
    
- Downstream Analysis (Trend + ML/Physics-informed ML)  
      
    
- Discussion  
      
    
- Limitations  
      
    
- Conclusion  
      
    

Even if Results are empty today, the paper becomes clearer immediately.

---

# One supervisor-ready framing line

You can say:

Since the final predictive outcome depends on literature coverage and data consistency, I am structuring the work as an evidence-grounded dataset and curation pipeline paper with zT as the primary target, secondary thermoelectric metrics as fallback targets, and downstream trend/ML analyses scoped according to data quality.

  
**