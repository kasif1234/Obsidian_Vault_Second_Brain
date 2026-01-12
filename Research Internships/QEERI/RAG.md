Load python libraries which are toolboxes for your task
YouTube video I used to write this content: https://www.youtube.com/watch?v=swvzKSOEluc -> THIS HAS LABS FOR EXERCISE

1. KEYWORD Search - TF-IDF & BM25 ///VS/// Semantic Search -> Preserves meaning

2. Embedding Models -> HF Has a Embedding Leader Board
	1.   Sentence Similarity models -> load form hugging face
	2. 
3. Vector databases
	1. Implementations -> (For Experimentation(Chroma), For Production (Pinecone, Weaviate) )
		1. ChromaDB -> default : Not persistent, when u create a chromo client in memory, so when ur program stops all data is lost so use chromadb.PersistentClient(path="./chroma.db"), now it can be used for production
4. Chunking -> Precision problem, u have to choose correct strategy here
		![[Pasted image 20260104092927.png]]
	1. Fixed-size Chunking + Overlaps
	2. Sentence Based Chunking
	3. Paragraph Based Chunking
	4. Semantic Chunking
	5. Agentic Chunking
5. Caching, Monitoring, Error Handling
	1. Rag systems are generally slow so optimization is required
	2. Cache repetitive parts of pipeline
			![[Pasted image 20260104093322.png]]
		1. Query Cache -> Normal Vs (Redis cache -> **Redis is a type of cache**, specifically a **distributed in-memory cache**.)
	3.  Monitoring
		1. ![[Pasted image 20260104093745.png]]
	4. Error Handling
		1. LLM could go down, network could give timeout, so we need a policy to handle error handling
6. RAG in Production
	1. Runs in Kurbenetes
		1. ![[Pasted image 20260104094035.png]]
7. Advanced Topics
	1. ![[Pasted image 20260104094105.png]]



============================================================
Python Libraries -> RAG = Loader → Chunker → Embedder → Vector DB → Retriever → LLM → Cache
### 1. Document loading and parsing

Used to read PDFs, text, web pages.

- `langchain`
    
- `llama-index`
    
- `pypdf`
    
- `PyMuPDF`
    
- `unstructured`
    

---

### 2. Text chunking

Break large documents into manageable pieces.

- `langchain.text_splitter`
    
- `llama_index.node_parser`
    

---

### 3. Embedding models

Convert text into vectors.

- `sentence-transformers`
    
- `openai`
    
- `huggingface_hub`
    
- `transformers`
    

---

### 4. Vector databases (retrieval core)

Store and search embeddings.

- `faiss`
    
- `chroma`
    
- `weaviate`
    
- `pinecone`
    
- `qdrant`
    

---

### 5. LLMs (generation)

Generate final answers.

- `openai`
    
- `transformers`
    
- `ollama`
    
- `vllm`
    

---

### 6. Orchestration frameworks (glue)

Connect retrieval + generation cleanly.

- `langchain`
    
- `llama-index`
    

---

### 7. Caching (important for scale)

Avoid recomputation.

- `redis`
    
- `diskcache`
    
- `joblib`
    

---

### 8. Optional but powerful

- Evaluation: `ragas`
    
- Monitoring: `langsmith`
    
- APIs: `fastapi`
    
- Async: `asyncio`