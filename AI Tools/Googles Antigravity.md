The term "Google Antigravity tool" refers to **[Google Antigravity](https://antigravity.google/)**, an **agentic development platform** (an AI-powered Integrated Development Environment, or IDE) that ==allows AI agents to autonomously plan, execute, test, and verify complex software development tasks==. It is not a single "tool" in the traditional sense, but a complete environment for building applications with the help of artificial intelligence.

![[Pasted image 20260115131122.png]]
Video (The NEW AI Tool EVERYONE Needs To Learn (Google Antigravity)) - https://www.youtube.com/watch?v=ns5yYA_nh3Y

==Quick Information==
1. Create a Markdown file -> Instruction Manuals
	1. .html - Web page structure
	2. .css - web page styling
	3. .js - Interactive features (respond to button clicked)
2. .env -> Store keys, database passwords and other sensitive information
3. ==C.O.R.E Framework -> How to organize these files==
	1. C -> Command (gemini.md)
		1. A .md file that tells the Ai WHAT ITS HIGH ELVEL INSTRUCTIONS ARE
		2. Sets the personality, goals, and behaviour guidelines when generating code
		3. For example -> helps to organize files, fix broken workflows, and find the correct files
	2. O -> Operations (/ops/): Here we are setting guardrails, cause ai is not deterministic (diff output for same input)
		1. For every task or workflow you have, there should be a corresponding .md file
		2. Example - test-app.md, deploy-project.md, build-website.md
	3. R -> Resources (/resources/):
		1. Each .md file should point to at least 1 .py file in its workflow 
	4. E -> Environment (/env/): -> behind the scenes that keeps the infrastructure running
		1. Temp files, logs, and assets, secret keys 

Basics of Google Antigravity:
1. 