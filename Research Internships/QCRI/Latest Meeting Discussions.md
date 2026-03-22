==ENTIRE PORJECT:==This sits at the intersection of a few fields.

- **Databases**  
    SQL semantics, query equivalence, query optimization theory (when two queries mean the same thing).
    
- **Formal methods and program verification**  
    Trying to “prove” two programs (here, SQL queries) are equivalent, or at least verifying with strong checks.
    
- **Natural Language Processing (NLP)**  
    Paraphrasing, meaning preservation, semantic similarity.
    
- **Semantic parsing (NL to SQL)**  
    Building and evaluating models that translate natural language questions into SQL.
    
- **Data-centric ML and benchmark construction**  
    Creating high quality datasets and using automatic filters (like the 66 percent rule) to keep only correct paraphrases.
    

So the study area is basically: **NLP + databases**, with a verification flavor from **formal methods**.

==Project Definition:== **Generate paraphrases of NLQ that remain SQL-equivalent, then validate them using strong evaluation (ensemble NL2SQL + multi-instance DB + formal SQL equivalence), and rank them by diversity.**

==02/02/2026==
He sent emails 

![[QCRI – Paraphrasing Project (09_02_2026).pptx]]

09/02/2026
==
TODO: 
1. LR - In Email
2. Get key phases and expand knowlede
3.  ![[How-to-write-a-great-research-paper.pdf]]

16/02/2026
==
1. How does Rayyan AI work?
2. Domain: Question Paraphrasing
3.  50 papers -> 10-20 Cite them -> Use 5 for comparison



==
## 1. Competitors (Text-to-SQL + Paraphrasing + Augmentation)

- “Text-to-SQL Data Augmentation via Paraphrasing”
    
- “Paraphrase Generation for Text-to-SQL Benchmarks”
    
- “Benchmark Augmentation for Natural Language to SQL”
    
- “Synthetic Data Generation for Text-to-SQL”
    
- “Question Rewriting for Text-to-SQL”
    
- “Improving Text-to-SQL Generalization with Data Augmentation”
    
- “Large Language Models for Text-to-SQL Dataset Generation”
    
- “Schema-aware Paraphrasing for Text-to-SQL”
    
- “Template-based Text-to-SQL Data Generation”
    
- “Spider dataset augmentation paraphrase”
    

## 2. SQL Equivalence / Query Equivalence / Formal Verification

- “SQL Query Equivalence Checking”
    
- “Query Equivalence Decider SQL”
    
- “Formal Verification of SQL Queries”
    
- “Bag Semantics Query Equivalence”
    
- “Constraint-based SQL Query Equivalence”
    
- “SMT-based SQL Query Equivalence”
    
- “Testing SQL Query Equivalence”
    
- “Proving Equivalence of SQL Queries”
    
- “Symbolic Execution for SQL Query Verification”
    
- “SQL Equivalence Verification Tool”
    

## 3. Diversity Metrics for Paraphrases

- “Paraphrase Diversity Metrics”
    
- “Self-BLEU Diversity Evaluation”
    
- “Distinct-n Diversity Metric for Text Generation”
    
- “Lexical Diversity Metrics for Paraphrase Generation”
    
- “Measuring Diversity in Natural Language Generation”
    
- “Jaccard Similarity for Paraphrase Diversity”
    
- “Diversity-Promoting Text Generation”
    
- “Diversity Evaluation for Paraphrase Models”
    
- “N-gram overlap metrics for paraphrase diversity”
    
- “Semantic similarity vs diversity in paraphrase generation”
    



===
09/03/2026
==
Analyze my literature review around these three themes. For each theme, identify the most relevant papers, extract the core method, evaluation approach, findings, limitations, and how each paper relates to my research goal. Organize the review by themes rather than paper-by-paper summary, and help me identify the research gap.

Theme 1: SQL Equivalence  
Research question: How can automatically generated Text-to-SQL paraphrases be verified to preserve the exact SQL meaning of the original question?  
Focus on papers discussing execution-based validation, semantic equivalence, SQL-aware verification, NL-SQL correspondence checking, and methods beyond exact string match. Likely relevant/anchor papers: Text2SQL-Flow: A Robust SQL-Aware Data Augmentation Framework for Text-to-SQL, and Semantic Decomposition of Question and SQL for Text-to-SQL Parsing.

Theme 2: Linguistic Diversity  
Research question: How can linguistic diversity in Text-to-SQL paraphrases be measured and filtered so the generated questions are meaning-preserving but phrased differently enough to improve robustness?  
Focus on papers discussing paraphrase diversity, realistic reformulations, lexical and structural variation, robustness to rewording, and filtering of semantically equivalent but linguistically diverse questions. Likely relevant/anchor papers: Improving Generalization in Semantic Parsing by Increasing Natural Language Variation in Training Data, and Evaluating NL2SQL via SQL2NL.

Theme 3: Competitor / Comparative Methods  
Research question: How does the proposed paraphrase-generation and validation pipeline compare with existing Text-to-SQL augmentation or robustness methods in producing correct and diverse training data?  
Focus on competitor methods such as synonym substitution, adversarial robustness methods, LLM-based paraphrase generation, SQL-aware augmentation pipelines, and robustness-oriented data augmentation. Likely relevant/anchor papers: Towards Robustness of Text-to-SQL Models against Synonym Substitution, and Text2SQL-Flow: A Robust SQL-Aware Data Augmentation Framework for Text-to-SQL.

Also keep this literature review purpose in mind:  
A literature review means finding the most relevant papers on the topic, then extracting their main method, results, and limitations.  
Next, compare papers by themes such as SQL equivalence, linguistic diversity, and robustness, instead of summarizing them one by one.  
Finally, identify the gap: what existing work still does not solve, which becomes the motivation for my own study.

# Key technical differences between your system and the competitor

Through the conversation, they identify these differences:

### Difference 1: Source of SQL

**Competitor:** uses gold SQL already موجود in Spider/BIRD.  
**Your system:** generates new SQL from schema.

### Difference 2: Diversity checking

**Competitor:** does semantic/grammar checking, but no strong diversity checker.  
**Your system:** includes a diversity checker.

### Difference 3: Number of NL2SQL evaluators

**Competitor:** one evaluator/model.  
**Your system:** three models.

### Difference 4: Similarity method

**Competitor:** uses a similarity approach like Sentence-BERT / embedding similarity.  
**Your system:** may use a different, possibly better but more expensive method.

==========================================================================================================================================================================================================================================================================================================================================================================================

Overall pipeline
==
https://chatgpt.com/c/69bb3785-2ae8-8391-a8c0-b2599f31c50a
## Compare and contrast

### 1. Starting point

**Competitor**

- Starts from an **existing benchmark example**.
    
- Extracts **gold SQL + schema + original NL query** from the test set.
    
- Uses these as fixed inputs.
    

**Your pipeline**

- Starts from the benchmark too, but then adds a **generation stage**.
    
- You use the **schema and conditions** to generate new SQL, verify it, then generate the corresponding NL question.
    

### Main difference

The competitor mostly **reuses benchmark gold SQL**.  
Your pipeline tries to **construct a new validated SQL–NL pair** before paraphrasing.

---

### 2. Role of SQL2NL

**Competitor**

- Uses SQL2NL directly to create **k paraphrased NL queries** from the gold SQL.
    

**Your pipeline**

- Uses the model first to generate SQL, then generate an **original NL question**, and after that enters the **NL2NL paraphrasing stage**.
    

### Main difference

The competitor’s paraphrasing is more direct:  
**gold SQL → paraphrases**

Your pipeline is more layered:  
**schema → SQL generation → SQL verification → NL generation → NL paraphrasing**

So your system is **more constructive**, while theirs is **more benchmark-driven**.

---

### 3. Validation of paraphrases

**Competitor**

- Uses **human semantic similarity / confidence score** to check whether paraphrases preserve meaning.
    

**Your pipeline**

- Uses **automatic filtering modules** like:
    
    - diversity checker
        
    - semantic checker
        
    - other methods
        

### Main difference

The competitor relies more on **human-in-the-loop semantic validation**.  
Your pipeline is trying to build a more **automatic quality control pipeline**.

This is important because their method may be more interpretable, but yours is potentially more scalable.

---

### 4. Evaluation stage

**Competitor**

- Sends the validated paraphrases into **one NL2SQL model**.
    
- Measures robustness with **execution-match accuracy** across paraphrases.
    

**Your pipeline**

- Sends original and paraphrased queries into **three standard NL2SQL models**.
    
- A paraphrase is judged good depending on how many models pass.
    

### Main difference

The competitor evaluates robustness with respect to **one parser/model**.  
You evaluate robustness against **multiple parsers**, so your notion of “good paraphrase” is more **model-agnostic**.

That is actually one of your strongest differences.

---

### 5. Definition of robustness

**Competitor**

- Robustness = whether paraphrased NL still leads to correct SQL execution in their NL2SQL setup.
    

**Your pipeline**

- Robustness = whether **multiple NL2SQL models** still succeed on both:
    
    - original query
        
    - paraphrased query
        

### Main difference

The competitor asks:  
**“Does this paraphrase survive one model?”**

You ask:  
**“Does this paraphrase preserve meaning strongly enough to survive across several models?”**

So your definition is **stricter and broader**.

---

## Big-picture contrast in one sentence

**Competitor pipeline:** benchmark-based, single-model, human-semantic-validation, execution robustness.  
**Your pipeline:** generation-heavy, automatically filtered, multi-model, consensus-based robustness.

---

==Now the important question:==
## Why choose 2/3 models passing?

This is actually a **majority-vote threshold**.

You can justify **2/3** much better than 1/3 or 3/3.

---

## Why not 1/3?

Because **1/3 is too weak**.

If only one model passes, that could mean:

- the paraphrase is genuinely good, or
    
- one model is unusually tolerant, lucky, or biased
    

So 1/3 does **not give enough confidence** that the paraphrase preserved meaning.

In paper language:

> A 1-of-3 criterion is too permissive, since success on only one parser may reflect parser-specific bias rather than true semantic preservation.

---

## Why not 3/3?

Because **3/3 is too strict**.

Even if a paraphrase is perfectly valid, one of the three NL2SQL models may fail because of:

- decoding randomness
    
- parser weakness
    
- schema-linking error
    
- model-specific phrasing sensitivity
    

So requiring 3/3 may reject many **actually good paraphrases** just because one model is brittle.

In paper language:

> A 3-of-3 criterion is overly conservative, as it may wrongly reject valid paraphrases due to failure of a single brittle parser.

---

## Why 2/3 makes sense

Because 2/3 is the **middle ground**:

- stricter than 1/3, so it avoids weak evidence
    
- less brittle than 3/3, so it tolerates one model’s failure
    
- reflects **majority agreement**
    
- reduces dependence on any single model
    

So the real logic is:

> A paraphrase should be considered valid if its semantic equivalence is supported by a majority of independent NL2SQL evaluators.

That is your cleanest justification.

---

# Strong justification you can write

You can say:

> We adopt a 2-of-3 agreement rule to determine paraphrase validity. This threshold reflects majority consensus across diverse NL2SQL models. A 1-of-3 rule would be too permissive and vulnerable to model-specific success, while a 3-of-3 rule would be too strict and likely reject semantically valid paraphrases due to the brittleness of an individual parser. Thus, 2-of-3 provides a practical balance between reliability and tolerance to isolated model failures.

That is probably the best direct answer for your report.

---

# Even better: how to justify it scientifically

Do **not** make it sound arbitrary. Say it is a **design choice**, then support it with analysis.

## Best way

Run a **threshold sensitivity analysis**:

- threshold = 1/3
    
- threshold = 2/3
    
- threshold = 3/3
    

Then compare:

- number of paraphrases accepted
    
- execution consistency
    
- semantic quality
    
- downstream robustness scores
    

If 1/3 accepts too many noisy paraphrases and 3/3 rejects too many useful ones, then 2/3 becomes empirically justified.

This is much stronger than just saying “we chose it.”

---

## What each threshold means conceptually

### 1/3

High recall, low precision  
Accepts many paraphrases, including weak ones

### 2/3

Balanced precision and recall  
Good compromise

### 3/3

High precision, low recall  
Very strict, may over-reject

So 2/3 is usually the most defendable if your goal is **reliable but not overly harsh** paraphrase selection.

---

# One more important thing

Your three models should ideally be described as:

- different architectures, or
    
- different fine-tunings, or
    
- different parsers
    

Because if the 3 models are extremely similar, then “2/3 vote” is less meaningful.  
But if they are meaningfully different, then majority agreement becomes a much stronger signal.

---

# Clean compare/contrast paragraph you can copy

Your pipeline differs from the competitor’s pipeline in both structure and evaluation philosophy. The competitor begins with benchmark gold SQL, schema, and original NL queries, then uses a SQL2NL model to generate paraphrases, validates them semantically with human confidence measures, and evaluates robustness using a single NL2SQL model through execution-match accuracy. In contrast, our pipeline includes an additional generation and verification stage, where SQL queries are first generated and validated before producing the original NL query. Paraphrases are then filtered automatically using semantic and diversity checks, and robustness is evaluated using three NL2SQL models rather than one. This makes our framework less dependent on a single parser and allows paraphrase quality to be assessed through cross-model agreement.

---

# Clean 2/3 justification paragraph you can copy

We use a 2-of-3 model agreement criterion to classify a paraphrase as valid because it provides a balanced majority-vote decision. A 1-of-3 threshold would be too permissive, as success by only one model may reflect model-specific behavior rather than genuine semantic preservation. In contrast, a 3-of-3 threshold would be too strict, since even a valid paraphrase may fail on one model due to parser brittleness or schema-linking limitations. Therefore, the 2-of-3 rule offers a practical compromise, ensuring that accepted paraphrases are supported by more than one model while remaining robust to isolated failures.

If you want, I can turn this into a **left-vs-right comparison table** exactly matching your supervisor’s “same theme on the left” style.

==============================================================================================================================

Strong experimental design
==

You can structure it like this:

### Setting A: Common benchmark setting

Both methods use:

- same benchmark gold SQL
- same schema
- same original NL
- same downstream NL2SQL evaluators

This should be your **main fair comparison**.

### Setting B: Extended generation setting

Only as an extra experiment:

- your pipeline generates new validated SQL–NL pairs

This becomes an **extension**, not the main comparison.




Paper Story
==
This paper presents a paraphrase validation framework for NL2SQL robustness evaluation. Unlike prior approaches that rely primarily on single-model execution outcomes or human confidence judgments, our method combines automatic semantic and diversity filtering with cross-model agreement over multiple NL2SQL parsers. By keeping benchmark inputs fixed and varying only the validation framework, we enable fair comparison with existing baselines. Experimental results show that majority-based agreement provides a more reliable criterion for paraphrase acceptance than either permissive single-model success or overly strict unanimous agreement.

Another Paper Story
==
The current framework has several limitations that create opportunities for improvement. It relies on a single unified model for both SQL2NL and NL2SQL, which may introduce self-consistency bias, and evaluates robustness with only one downstream NL2SQL parser, making the results model-specific. Semantic validation depends on human confidence scoring, which is expensive and difficult to scale. In addition, the pipeline does not explicitly enforce paraphrase diversity, assumes the correct schema is already available, and does not address ambiguous, unanswerable, or multi-turn queries. Although execution-match accuracy is a strong metric, it may still hide semantic errors in cases where different SQL queries return the same result. The framework is also computationally costly and may not generalize well across broader real-world settings. These limitations suggest improvements through multi-model evaluation, automatic semantic and diversity filtering, schema retrieval integration, broader query types, and clearer acceptance criteria.