Main Google Docs: https://docs.google.com/document/d/1w1Ry2h3uIUCBiI7pVEIKrJIphzOtULTkwDF2NO1qBmk/edit?usp=sharing
Main Google Sheets: https://docs.google.com/spreadsheets/d/12Ly4PHFVLOvNFjs6EU-7kbMJFKYLIpz4VuOp7WtN-_c/edit?usp=sharing

02/02/2026
==
1. Do Literature review

09/02/2026
==
1. [Review Paper] - [A Review of Driving Simulation Technology
and Applications] - [2020] -> A driving simulator feels real when the car physics, motion cues, and virtual world (visuals, sound, traffic, weather) all match what your senses expect.
Hardware limits what the system can physically do, and the algorithms decide how to use those limits to produce the most believable sensations.
2. [Article (New study)] - [Designing and Planning of Studies of Driver Behaviour at
Pedestrian Crossings Using Whole-Vehicle Simulators] - [2024] -> It is a step by step guide for designing a whole-vehicle simulator experiment on driver behaviour at pedestrian crossings, listing what to vary (signage, crossing context, vulnerable user behaviour, distractors, speed, weather).
It also gives a ready repeatable scenario plan (30 drivers, multiple environments, 20 crosswalks per run, N-back and SuRT distraction tasks) and how to run it safely (training, ethics, reduce simulator sickness)
3. [Systematic Paper] - [Driving simulator validation studies: A systematic review] - [2025] -> This systematic review summarizes how driving simulators are validated (scenarios, metrics, stats, questionnaires, physio tools) and how DOF, fidelity, and simulator sickness affect validity, proposing reference standards. 
	Absolute validity = simulator matches real driving in the actual numbers
	Relative validity = it matches the same patterns/trend even if numbers differ.
4. [Research Article] - [Driving Simulator Validity of Driving Behaviour in Work Zones
] - [2020] -> They tested work zone driving in both a real field study and an 8 DOF simulator, then compared speed, car following (distance, headway) and reaction delay time, using standard stats plus survival analysis (Kaplan Meier and Cox) for the delay time.
Many metrics showed absolute validity (spot speed, mean distance, mean headway, reaction delay), SD distance showed only relative validity, while speed reduction rate and SD headway failed, and simulator driving looked more aggressive.
5. [Systematic Review] - [A systematic review of abnormal behaviour detection and analysis 
in driving simulators] - [2025] -> This 2025 Transportation Research Part F paper is a systematic review (2013–2023) of how driving simulators are used to detect and analyse unsafe driving behaviours, filtering 759 records down to 70 studies using PRISMA.
It shows most studies combine vehicle measures (especially SDLP, speed, steering) with driver measures (especially eye activity and reaction time), and most experiments use fixed simulators, while higher-DOF, higher-fidelity rigs are recommended for realism.
Method-wise, SVM and Random Forest dominate behaviour detection, ANOVA and t-tests dominate impact analysis, and the big gap is studying combined risks plus harder environments (slippery roads, low visibility, unforeseen events) rather than single behaviours in simple scenarios.

16/02/2026
==
TODO:
![[Pasted image 20260214103457.png]]
![[Pasted image 20260223085046.png]]
1. [Infrastructure] “How do we build a simulator that feels real enough to study behaviour?”
2. [Experimental Design] “How do we properly design a driving behaviour experiment?”
	1. {Different signage systems (normal signs vs flashing vs VMS signs)}
3. [Scientific Credibility] “Can we trust behaviour results from simulators?”
	1. - **Absolute validity** → Simulator results ≈ real-world results (no significant difference).
	2. **Relative validity** → Trends are similar, even if numbers differ.
4. [Experimental Comparison] “Does behaviour in simulator match behaviour in real road conditions?”
	1. Survival analysis is a statistical method used to model **time until an event occurs**, while properly handling incomplete and non-normal data. They used it for reaction Time.
5. [Behaviour Analysis & AI] “How do we detect unsafe driving behaviour using simulator data?”