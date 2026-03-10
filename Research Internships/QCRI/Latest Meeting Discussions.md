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