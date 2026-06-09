==Overall Approach== - Natural Language Processing
1.  Complete Experimentation Write-Up {Justify each decision}
2.  Code Clearly and Run
3. Improve Paper with Results
Learn: [NL2SQL Systems, Andrew.ng Sequence Models Complete Course, Hugging Face, sPAcy]
===============================================================
Text to SQL systems ->
- [Pre-Processing, Translation, Post Processing]
	- Pre-processing -
		- Schema Linking, Database content retrieval, Additional info acquisition
	- Translation - 
		- **Encoding strategy** - [Sequential encoding (tokens), Graph Based encoding, Separate encoding]
		- **Decoding strategy** - [Greedy search, Beam search, Constraint-aware decoding]
		- **Prompt strategy** - [Chain-of-thought, Decomposition]
	- Post-Processing - 
		- SQL correction
		- Output consistency
		- Execution-guided checking
		- N-best reranking
- [Evaluation]
	- Execution Accuracy
	- String-Match Accuracy
	- Component-Match Accuracy
- [Open Problems]
	- Open-domain Text-to-SQL
	- Cost-effective Text-to-SQL
	- Trustworthy Text-to-SQL
	- Better adaptation to new domains

===============================================================
**Learn Notes:**
1.  ==NL2SQL Systems: ==
2. ==Andrew.ng Sequence Models Complete Course==
3. ==Hugging Face==
4. ==sPAcy==

===============================================================
**Resources:**
1. NA
2. Andrew.ng Sequence Models Complete Course: https://www.youtube.com/watch?v=S7oA5C43Rbc&list=PLcCe-ymWq77rAjKSMY1iRW4ID8byUSOBs

===============================================================
**Important Advice:**
1. Read 3 to 4 Strong Survey Papers on nl2sql systems, fully understand them before replicating
2. Your experimentations should improve the confusion matrix. Talk like this: "this will reduce False negatives"
===============================================================
==Code Understanding==:
run_original_pipeline.py
= The boss/controller file. It controls the full experiment from data loading to saving results.

llama_3_1_8B.py
= The model file. It only handles prompting, Llama generation, batching, and SQL cleanup.

sql_utils.py
= The database/helper file. It handles schema extraction, database querying, and SQL result comparison.

==========
run_original_pipeline.py
Main controller file
│
├── Loads Spider dev.json questions
├── Loads Spider tables.json schemas
├── Creates schema cache
├── Sends batches to Llama model
│   │
│   └── llama_3_1_8B.py
│       Model wrapper file
│       ├── Loads tokenizer -> Autotokenizer
│       ├── Loads vLLM model -> from vllm import LLM, SamplingParams
│       ├── Builds NL2SQL prompt 
│       ├── Generates SQL
│       └── Cleans generated SQL -> re
│
├── Evaluates generated SQL
│   │
│   └── sql_utils.py
│       SQL helper file
│       ├── Loads schemas
│       ├── Extracts readable schema text
│       ├── Runs generated SQL -> sqlite3
│       ├── Runs gold SQL
│       └── Compares both outputs
│
└── Saves final results to CSV