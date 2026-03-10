1. Competitor
2. SQL Equivalence
3. Diversity


==Paper will look like==

## 1. Introduction

You explain the problem:  
Text-to-SQL systems need more training data, and paraphrasing can help, but only if the new question still means the **exact same SQL** and is also **worded differently enough** to be useful. That is the whole motivation of your paper.

Pasted text

## 2. Problem Statement

Here you clearly define your research question:  
How can we build a pipeline that keeps only paraphrases that are:

- **SQL-equivalent** to the original
    
- **linguistically diverse** from the original
    

So your paper is not mainly “how to generate paraphrases.”  
It is more like:  
**“How do we validate and rank paraphrases correctly for Text-to-SQL augmentation?”**

## 3. Related Work / Literature Review

This section will review:

- SQL equivalence methods
    
- semantic similarity baselines like SBERT
    
- diversity metrics like Jaccard and BLEU
    
- existing competitor methods
    

Your professor clearly wants this part to be strong, because he said the goal right now is to know **what exists** and **how your work compares to it**, not to invent a better method yet.

## 4. Proposed Pipeline

This is the heart of your paper.

The pipeline will likely be:

**Original NLQ → generate paraphrases → convert through NL2SQL / get SQL pairs → check SQL equivalence → keep only correct ones → measure diversity → rank/select best paraphrases**.

Pasted text

So your method is **hierarchical**:

- first check correctness with SQL equivalence
    
- then among the correct ones, measure diversity
    

## 5. SQL Equivalence Module

This section explains:

- you compare two SQL queries
    
- using the same schema
    
- possibly with constraints
    
- and the tool decides whether they are truly equivalent, even if written differently
    

This is your **semantic correctness filter**.  
That is a major part of your novelty.

## 6. Diversity Module

After correctness is guaranteed, you check how different the wording is.  
This is where metrics like:

- Jaccard
    
- BLEU
    
- maybe other diversity scores
    

will be used.

Important point:  
your professor is basically saying diversity should be checked **only after** semantic equivalence is confirmed.

## 7. Experimental Setup

Here you describe:

- dataset / benchmark
    
- original NLQs
    
- generated paraphrases
    
- SQL pairs
    
- schema availability
    
- thresholds or ranking strategy
    
- which baselines / competitors you compare against
    

You may also explain that human validation will be done on a sample, like checking top-ranked paraphrases manually.

Pasted text

## 8. Baselines and Competitors

This section compares your pipeline against:

- SBERT-style semantic similarity baselines
    
- simple diversity metrics
    
- maybe other augmentation or filtering methods from literature
    

Your professor wants this comparison to be central.

## 9. Results

This section will answer:

- How many paraphrases passed SQL equivalence?
    
- Among those, which were most diverse?
    
- How does your pipeline compare to baselines?
    
- Do embedding-based similarity methods fail on some examples?
    
- Does your approach better separate correctness from diversity?
    

## 10. Human Evaluation / Error Analysis

You will probably include:

- manual review of sampled paraphrases
    
- whether top-ranked paraphrases are truly good
    
- examples where semantic similarity score looks good but meaning is actually wrong
    
- examples where wording is very different but SQL meaning is still preserved
    

## 11. Conclusion

You will conclude something like:

A good Text-to-SQL paraphrase evaluation pipeline should not rely only on semantic similarity embeddings.  
Instead, it should first verify **SQL equivalence** for correctness, then evaluate **linguistic diversity** separately for usefulness in augmentation.

## In one line

Your paper will look like:

**“A pipeline paper for validating Text-to-SQL paraphrases using SQL equivalence first, then diversity scoring, with comparisons against existing baselines.”**

A possible title style could be:

**Evaluating Text-to-SQL Paraphrases with SQL Equivalence and Linguistic Diversity Metrics**

or

**A Hierarchical Validation Pipeline for Text-to-SQL Paraphrase Augmentation**

I can also draft the exact **IMRaD structure with subsection names** so it looks like a real paper outline.


Related Work Example
==
## 2. Related Work

### 2.1 Text-to-SQL evaluation and the need for semantic validation

Text-to-SQL research has traditionally relied on benchmarks such as Spider and on evaluation measures like exact match and execution accuracy. While these metrics are useful for assessing whether a predicted SQL query matches a reference query or produces the correct result on a given database, they are often insufficient for paraphrase validation. In paraphrase-based augmentation, the central question is not only whether a generated natural language question looks similar to the original, but whether it preserves the **same underlying SQL semantics**. This has created growing interest in methods that move beyond surface-form comparison and instead evaluate functional or semantic equivalence more directly.

### 2.2 SQL equivalence and functional validation methods

A major line of recent work focuses on verifying whether two SQL queries are truly equivalent in meaning. Formal approaches such as **SPES** attempt to prove equivalence through symbolic representations and containment checking. These methods are appealing because they provide mathematically grounded guarantees, but in practice they may be limited by incomplete support for the full SQL language and by implementation constraints.

More recent work has shifted toward hybrid and execution-aware methods. **SQLDriller** proposes a validation framework based on execution consistency, where carefully constructed database instances are used to expose semantic mismatches between SQL queries. By combining execution-based checks with stronger formal back-end verifiers, it aims to detect subtle logical differences such as incorrect join behavior that may not be visible from textual similarity alone. This makes it especially relevant for paraphrase pipelines where correctness must be verified automatically.

Another promising direction is database-free structural reasoning. **FuncEvalGMN** represents SQL queries as relational operator graphs derived from logical execution plans and compares them using graph matching networks. This avoids dependence on a physical database while still capturing the structural logic of the query. Such methods are important because they suggest that SQL equivalence can be approximated from query structure itself, rather than only from execution outputs.

Related work such as **CYCLESQL** approaches validation indirectly, using data-grounded natural language explanations and entailment checks to determine whether a SQL query faithfully reflects the original question. Although this improves interpretability and can serve as a feedback mechanism, it is still more heuristic than direct SQL equivalence checking and may be vulnerable to semantic drift.

Taken together, these studies show that recent evaluation research is moving toward **functional validation**, where semantic preservation is assessed through execution behavior, symbolic reasoning, or structural representations rather than simple string overlap.

### 2.3 Semantic similarity as a baseline for meaning preservation

Alongside SQL-aware validation, another body of work evaluates meaning preservation using semantic similarity models from NLP. Methods based on **SBERT**, **cosine similarity**, **BERTScore**, and related embedding techniques have been applied to compare the original question and its paraphrase in a shared semantic space. For example, work such as **Evaluating NL2SQL via SQL2NL** uses SBERT-style representations to assess whether paraphrased questions retain their semantic intent, while other studies such as **Redefining Text-to-SQL Metrics** incorporate specialized code-oriented embeddings as part of composite similarity metrics.

These approaches are useful because they are easy to implement, do not require a database, and provide graded similarity scores rather than binary judgments. However, they remain limited for Text-to-SQL validation. Natural language similarity does not necessarily capture SQL-specific logical distinctions. Two questions may appear semantically close in embedding space while differing in important query behavior, such as aggregation type, join conditions, or filtering constraints. For this reason, embedding-based similarity is better viewed as a **baseline** or supporting signal rather than a sufficient validator of semantic equivalence.

### 2.4 Linguistic diversity in paraphrase evaluation

Beyond semantic preservation, paraphrase augmentation also requires that new questions be phrased differently enough to improve model robustness. This motivates a second line of work on **linguistic diversity**. Traditional lexical metrics such as **BLEU**, **Jaccard similarity**, edit-distance-style overlap measures, and n-gram comparison have been used to quantify wording differences between paraphrases. These methods are simple and interpretable, but they mainly capture surface variation and often ignore deeper structural differences.

Recent work extends diversity evaluation to grammatical and structural features. For example, **grammatical similarity** based on dependency parse trees and part-of-speech distributions measures whether two paraphrases differ syntactically rather than only lexically. Other work studies **lexical complexity** and **syntactic complexity**, including features such as sentence length, dependency depth, lexical rarity, and lexical density. These measures are useful because they characterize whether paraphrases introduce richer variation in vocabulary and sentence structure, which is often the real objective in robustness-oriented data augmentation.

The literature therefore suggests that diversity should not be reduced to one metric alone. Lexical, syntactic, and grammatical measures each capture different aspects of variation, and together they offer a more complete picture of how a paraphrase differs from the source question.

### 2.5 Research gap and positioning of the present work

Although recent studies have advanced both semantic validation and diversity analysis, most existing methods emphasize one side more than the other. SQL-aware verifiers focus on whether meaning is preserved, while NLP-based diversity measures focus on whether phrasing changes. There is still limited work that integrates these two requirements into a single hierarchical pipeline for Text-to-SQL paraphrase selection.

This motivates the present study. The literature suggests that a reliable paraphrase evaluation pipeline should first verify **SQL equivalence** to ensure semantic correctness, and only then evaluate **linguistic diversity** among the semantically valid candidates. In this sense, the present work is positioned not as a new paraphrase generator, but as a validation and ranking framework that combines functional correctness with useful variation. Existing methods such as SQLDriller, FuncEvalGMN, CYCLESQL, and SBERT-based semantic metrics provide strong baselines for comparison, while grammatical and lexical diversity metrics provide complementary tools for measuring variation.

Overall Aim
==
“Researchers already know that paraphrases must preserve meaning and also be different in wording. Some papers are good at checking SQL meaning, others are good at measuring language variation, but there is still a need for a pipeline that combines both in the right order.”

Baselines Obtained
==

SQL Equivalence Tools

- **SQLDriller:** Detailed in **"Automated Validating and Fixing of Text-to-SQL Translation with Execution Consistency"** (Yang et al., 2025), this tool uses a necessary correctness condition called **execution consistency** to flag incorrect mappings by crafting database instances likely to reveal semantic violations.
- **FuncEvalGMN:** Detailed in **"Towards Database-Free Text-to-SQL Evaluation: A Graph-Based Metric for Functional Correctness"** (Zhan et al., 2025), this tool utilizes a **Relational Operator Tree (RelNode)** to extract semantic information from logical execution plans and performs graph matching without requiring a live database.
- **SPES:** Presented in **"SPES: A Symbolic Approach to Proving Query Equivalence Under Bag Semantics"** (Zhou et al., 2022), this is a **formal SQL equivalence verifier** that generates symbolic query representations to assess containment relationships.
- **CYCLESQL:** Introduced in **"Grounding Natural Language to SQL Translation with Data-Based Self-Explanations"** (Fan et al., 2024), this framework uses **data-grounded natural language explanations** and Natural Language Inference (NLI) to iteratively validate translation correctness rather than direct SQL-to-SQL comparison.

Diversity Tools

- **Evaluating NL2SQL via SQL2NL:** Found in the paper **"Evaluating NL2SQL via SQL2NL"** (Safarzadeh et al., 2025), this framework measures **grammatical similarity** using dependency parse trees and **semantic similarity** via Sentence-BERT embeddings to evaluate model robustness to linguistic variation.
- **Mitsopoulou et al.:** The paper **"Analysis of Text-to-SQL Benchmarks: Limitations, Challenges and Opportunities"** (2025) provides a methodology for dataset analysis focusing on **lexical complexity** (rarity, lexical density), **syntactic complexity** (dependency depth, sentence length), and structural variety in SQL.
- **BLEU / Jaccard:** **BLEU** is a traditional metric for lexical precision originally from **"BLEU: A Method for Automatic Evaluation of Machine Translation"** (Papineni et al., 2002). **Jaccard similarity** is utilized in the Mitsopoulou et al. (2025) paper to calculate **structural match** errors by comparing sets of structural components in subqueries.

Competitor Mapping
==

- **SQLDriller (2025):** The main competitor for **semantic correctness**, as it explicitly detects subtle errors like incorrect JOIN types that traditional metrics often miss.
- **FuncEvalGMN (2025):** A strong competitor for **database-free equivalence checking**, as it generalizes well to unseen datasets by focusing on relational operator structures.
- **CYCLESQL (2024):** A primary competitor for **feedback-based validation**, utilizing a unique "hybrid" semantic loop that combines data provenance with operation-level query semantics.
- **Evaluating NL2SQL via SQL2NL (2025):** The key competitor for measuring **semantic similarity and linguistic diversity**, establishing standard thresholds for paraphrase reliability.
- **Redefining Text-to-SQL Metrics (2025):** A competitor for **embedding-based similarity**, this paper (Pinna et al., 2025) introduces the **Query Affinity Score (QAS)**, which combines specialized code embeddings with execution result similarity.
- **Mitsopoulou et al. (2025):** A competitor for **diversity-focused evaluation**, providing fine-grained axes to analyze how well datasets (and by extension, generators) cover lexical and syntactic distributions


Latest Table
==
| Paper title                                                                                                     | Year | Task                                          | Method category                      | SQL equivalence method                                                                         | Semantic similarity method                                                        | Diversity metric                                                                                                                | Strengths                                                                           | Weaknesses                                                                                 | Suitable as competitor?                                 | Notes for my project                                                     |
| --------------------------------------------------------------------------------------------------------------- | ---: | --------------------------------------------- | ------------------------------------ | ---------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ | ------------------------------------------------------- | ------------------------------------------------------------------------ |
| **Automated Validating and Fixing of Text-to-SQL Translation with Execution Consistency (SQLDriller)**          | 2025 | Validation / correction                       | Hybrid execution + verifier          | Execution consistency with crafted database instances, backed by formal/bounded verifiers      | Limited / not main focus                                                          | Not main focus                                                                                                                  | Strong at detecting subtle SQL logic errors such as incorrect JOIN behavior         | Focused mainly on correctness, not diversity ranking; depends on quality of SQL candidates | **Yes**                                                 | Best main baseline for the **SQL equivalence stage** of your pipeline    |
| **Evaluating NL2SQL via SQL2NL**                                                                                | 2025 | Robustness evaluation / paraphrase evaluation | NLP-based evaluation framework       | Execution Match may be used, but not its core novelty                                          | Sentence-BERT embeddings for semantic similarity                                  | Grammatical similarity using dependency parse trees; lexical/semantic variation analysis                                        | Strong for evaluating linguistic variation and robustness in natural language       | Weaker for exact SQL logic than SQL-grounded verifiers                                     | **Yes**                                                 | Best baseline for the **diversity + semantic similarity** side           |
| **Towards Database-Free Text-to-SQL Evaluation: A Graph-Based Metric for Functional Correctness (FuncEvalGMN)** | 2025 | Evaluation                                    | Graph-based structural method        | Relational Operator Tree (RelNode) + graph matching on logical plans                           | May use representation similarity internally, but not as main NLP semantic metric | Not main focus                                                                                                                  | Database-free, captures structural SQL meaning well, generalizes to unseen datasets | Not a full paraphrase-selection pipeline; weaker on diversity side                         | **Yes**                                                 | Strong baseline for **database-free semantic correctness**               |
| **Grounding Natural Language to SQL Translation with Data-Based Self-Explanations (CYCLESQL)**                  | 2024 | Validation / correction                       | Feedback-based explanation framework | Indirect validation through data-grounded self-explanations, not direct SQL-to-SQL equivalence | NLI-based entailment between explanation and query intent                         | None                                                                                                                            | Interpretable and useful as a feedback loop                                         | Indirect; can drift semantically and is weaker than direct equivalence checking            | **Yes**                                                 | Useful comparison baseline for **explanation-based validation**          |
| **Analysis of Text-to-SQL Benchmarks: Limitations, Challenges and Opportunities (Mitsopoulou et al.)**          | 2025 | Dataset analysis / benchmark analysis         | Diversity-analysis framework         | None directly                                                                                  | None directly                                                                     | Lexical complexity, lexical density, syntactic complexity, dependency depth, sentence length, Jaccard-style structural analysis | Fine-grained view of dataset diversity and language variation                       | Does not verify exact SQL meaning                                                          | **Yes**                                                 | Best baseline for **diversity analysis after correctness is confirmed**  |
| **Redefining Text-to-SQL Metrics**                                                                              | 2025 | Metric design / evaluation                    | Embedding-based composite metric     | Includes execution-result-related components, but not a direct equivalence prover              | Specialized code embeddings with similarity scoring, part of Query Affinity Score | Includes ranking / affinity style comparison rather than pure diversity metric                                                  | More SQL-aware than generic SBERT baselines                                         | Still not a true SQL equivalence checker; can be complex and memory-heavy                  | **Yes**                                                 | Good competitor for **embedding-based semantic similarity**              |
| **SPES: A Symbolic Approach to Proving Query Equivalence Under Bag Semantics**                                  | 2022 | Formal verification                           | Symbolic / formal                    | Symbolic query representations and containment under bag semantics                             | None                                                                              | None                                                                                                                            | Mathematically grounded equivalence proof                                           | May have limited support for full SQL variants and practical pipeline integration          | **Yes**                                                 | Good formal baseline to show the **theory side** of equivalence checking |
| **BLEU: A Method for Automatic Evaluation of Machine Translation**                                              | 2002 | Automatic text evaluation                     | Lexical overlap metric               | None                                                                                           | None                                                                              | BLEU n-gram overlap                                                                                                             | Simple, widely known, easy to report                                                | Surface-level only; poor for SQL meaning and limited for deep paraphrase diversity         | **No** as a main competitor, **Yes** as a simple metric | Use as a **supporting diversity metric**, not as a main baseline paper   |
| **Spider: A Large-Scale Human-Labeled Dataset for Complex and Cross-Domain Semantic Parsing and Text-to-SQL**   | 2018 | Benchmark / dataset                           | Foundational benchmark               | Uses standard benchmark metrics like exact match / execution accuracy                          | None                                                                              | None                                                                                                                            | Foundational benchmark for Text-to-SQL evaluation                                   | Not a paraphrase-validation method and not a direct competitor                             | **No**                                                  | Cite as the **benchmark foundation**, not as a competing method          |

===============================================================

The **2 strongest** to use are:

1. **SQLDriller** — strongest for **SQL equivalence** and your main **competitor** on semantic correctness, because it directly checks whether the paraphrase preserves the exact SQL logic.
    
2. **Evaluating NL2SQL via SQL2NL** — strongest for **diversity** and your main **competitor** on the language side, because it measures semantic similarity plus grammatical/linguistic variation.
    

Why these 2:

- Together, they cover your whole project logic: **correct meaning first, then diverse wording**.
    
- In simple terms: **SQLDriller handles the “same SQL?” question, and SQL2NL handles the “different enough wording?” question.**
    

So your paper can basically compare against:

- **SQLDriller** for the **SQL equivalence stage**
    
- **Evaluating NL2SQL via SQL2NL** for the **diversity stage**