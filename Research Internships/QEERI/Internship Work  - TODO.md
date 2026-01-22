![[Pasted image 20260107061003.png]]

==OBJECTIVES==

These are pointers, take them deep and carry out intricate analysis
1. Implement RAG system in python with local LLM
	1. Output -> JSON with filled parameters
	2. ==Improve Implementation by using given libraires== 
2. Call the graph2table API using snippets
	1. Output -> CSV
	2. ==Research Conductive Polymers Extract them, then do a plot Together==
3. Show to Doctor 
	1. Output -> 20 Figures + JSONS & 1 big graph with all results combined {MATLABS/Excel}
	2. ==Figures + One Main plot + RAG System==
4. Come up with a workflow on your own methodology, show it to Dai Hai wan
	1. PowerPoint {draw.io, }
5. Machine Learning Work 
	1. Output -> Predict best Polymer

==Info to watch out for==
8/01/2026 -> Meeting with Dai Haiwen and Anas Abutaha to discuss progress and next steps
11/01/2026 -> Extracting key insights from our meeting
1. maybe automate via MCP later
2. Golden dataset = manually extracted, trusted, reviewed by multiple people and domain experts  && a Silver dataset = scaled using automation, guided by the golden examples
3. Convert PDFs to images, segment figures, then digitize plots. ==Pandoc can help convert PDFs to markdown and extract figures; segmentation tools can split multi-panel figures (A, B, C, etc.).==
4. DOI to PDF automation exists but has limitations for recent papers.
5. **For now (6–12 months goal):** they push the **golden dataset approach**, meaning **manual + strict standard + human agreement**, then later you can automate. That implies a **rule based + human validated workflow** as the core.
6. Build a production grade extraction system that the domain experts will actually trust (golden dataset first).
7. ![[Pasted image 20260111174952.png]]
12/01/2026
- Constructing the golden/silver dataset
- 
==============================================================
Example Of Good Snippets
- . (GDOS) Tuning charge transport dynamics via clustering of doping in organic semiconductor thin films
![[Pasted image 20260103201528.png]]
-  (GDOS) Tuning charge transport dynamics via clustering of doping in organic semiconductor thin films [Same as above (1)]
![[Pasted image 20260103202302.png]] 
- Charge-transport model for conducting polymers
![[Pasted image 20260105072206.png]]
![[Pasted image 20260103205031.png]]

![[Pasted image 20260103205057.png]]
![[Pasted image 20260105072905.png]]
![[Pasted image 20260103205117.png]]
![[Pasted image 20260105072339.png]]


![[Pasted image 20260103205137.png]]


==================
OUTCOME
![[Pasted image 20260105095631.png]]

![[Pasted image 20260105103013.png]]
====
Extraction from 2 papers combined {Log scaled graphs}
![[Pasted image 20260106201240.png]]
![[Pasted image 20260106201203.png]]


18/01/2026
19/01/2026
20/01/2026
polymer, solvent, dopant, doping method, doping level, film preparation method, thickness, annealing, σ, S, temperature, reference (DOI), evidence location