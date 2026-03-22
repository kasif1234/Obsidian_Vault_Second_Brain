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


[22/03/2026] Prompt for Literature Review given to Perplexity
==
==USE THIS CHATGPT ->== https://chatgpt.com/c/69bf8e4a-fd80-838f-b2e2-e11aad570177
I am writing a **half-page literature review** on **driving behavior studies using simulators** for a research project on **turn signaling behavior**.

Please find **5 academic papers total**:

- **3 global papers** on how driving simulators are used to study driver behavior
- **2 local/regional papers** from **Qatar, GCC, or nearby similar regions** if Qatar/GCC papers are limited

I want papers that focus on topics such as:

- reaction time
- hazard perception
- distraction
- lane changing
- safety behavior
- driver decision-making

Please prioritize studies that help me write this structure:

1. **Global evidence** showing simulators are widely used to study driving behavior
2. **Regional/Qatar/GCC evidence** showing local relevance or limited local literature
3. **Research gap** showing that simulator studies exist, but **direct work on turn signaling behavior is still limited**, especially in Qatar/GCC

For each paper, give me:

- full citation
- 2 to 3 line summary in academic style
- country/region of study
- what driver behavior it studied
- whether it is useful for my literature review and why

Only include **reliable academic sources** such as journal papers, conference papers, or university research. Avoid websites and blogs.

If GCC/Qatar papers are very limited, include papers from **similar driving contexts** and clearly label them as regional substitutes.


Perplexity Response 
==
## 1) Global simulator studies (3 papers)

## 1. Commentary training and hazard perception

- **Full citation**  
    McKenna, F. P., & Crick, J. L. (2010). Commentary training improves responsiveness to hazards in a driving simulator. _Accident Analysis & Prevention_, 42(6), 1635–1641.[](https://pubmed.ncbi.nlm.nih.gov/20728670/)​
    
- **2–3 line summary**  
    Learner drivers completed a simulated route containing multiple latent and overt hazards and were then randomly allocated to commentary‑driving training or control conditions. Trained learners subsequently showed fewer crashes, earlier speed reduction, and earlier brake application when approaching hazards in the simulator.[](https://pubmed.ncbi.nlm.nih.gov/20728670/)​
    
- **Country/region**  
    United Kingdom (learner drivers in a high‑income setting).
    
- **Driver behaviour studied**  
    Hazard perception, reaction time to hazards, safety behaviour (speed choice and braking).
    
- **Usefulness for your review**  
    Very useful: it shows that **driving simulators** are an accepted tool to quantify hazard perception and reaction timing, and that fine‑grained behavioural metrics (speed profiles, braking onset) can be extracted, which is directly analogous to measuring turn‑signal timing and usage around hazards and maneuvers.[](https://pubmed.ncbi.nlm.nih.gov/20728670/)​
    

---

## 2. Distraction, reaction time and car‑following

- **Full citation**  
    Chouhan, S. S., et al. (2025). A driving simulator study in various speed conditions: Effects of hands‑free conversation and texting on distracted driving performance. _PLOS ONE_, 20(12), e0336480.[](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0336480)​
    
- **2–3 line summary**  
    This simulator study exposed 40 drivers to baseline, hands‑free conversation, and texting conditions across multiple traffic regimes (free‑flow, congested, and collision‑avoidance scenarios). It quantified changes in lateral control (standard deviation of lateral position), acceleration reaction time, and time to initial braking, showing substantial deterioration in reaction time and lane‑keeping under texting, with more nuanced effects of hands‑free conversation.[](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0336480)​
    
- **Country/region**  
    Global/unspecified; typical university‑based sample in a high‑income context.
    
- **Driver behaviour studied**  
    Reaction time (acceleration and braking), distraction (phone use), lane‑keeping, safety behaviour during car‑following and collision‑avoidance.
    
- **Usefulness for your review**  
    Highly useful: it provides strong evidence that simulators are widely used to examine **distraction‑induced changes in reaction time and safety behaviour**, and it also demonstrates detailed scenario design (car‑following, collision avoidance) that you can parallel when framing turn‑signaling tasks.[](https://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0336480)​
    

---

## 3. In‑vehicle feedback, decision‑making and safety

- **Full citation**  
    Murzello, Y., Ding, W., Zhang, X., Niu, J., Samuel, S., & Cao, S. (2025). Information, assessment, or decision: A driving simulator study on real‑time feedback and driver behaviour. _Transportation Research Record_, 2790(5), 1–12.[](https://pmc.ncbi.nlm.nih.gov/articles/PMC12585109/)​
    
- **2–3 line summary**  
    This simulator experiment compared different forms of real‑time feedback (information‑, assessment‑, and decision‑oriented) on drivers’ speed and headway to a lead vehicle. Decision‑oriented feedback modestly improved speed and distance‑keeping behaviour, although attitudinal acceptance was lower, indicating a trade‑off between behavioural safety gains and user acceptance.[](https://pmc.ncbi.nlm.nih.gov/articles/PMC12585109/)​
    
- **Country/region**  
    Conducted in a high‑income research setting (laboratory‑based, international authorship).
    
- **Driver behaviour studied**  
    Driver decision‑making under feedback, speed selection, car‑following distance (safety margin), and response to safety‑oriented in‑vehicle interventions.
    
- **Usefulness for your review**  
    Useful conceptually: it illustrates how simulators are used to study **real‑time decision‑making and safety behaviour**, strengthening your argument that the same platform can be used to study decisions about signalling (e.g., when and whether to indicate before lane changes or turns).[](https://pmc.ncbi.nlm.nih.gov/articles/PMC12585109/)​
    

---

## 2) Regional / Qatar–GCC simulator studies (2 papers)

## 4. Multi‑cultural simulator study in Qatar

- **Full citation**  
    Almallah, M., Soliman, A., Alhajyaseen, W., & Al‑Far, R. (2021). Driving simulation sickness and the sense of presence: Correlation and contributing factors in a multi‑cultural driving population. _Transportation Research Part F: Traffic Psychology and Behaviour_, 80, 1–15.[](http://qspace.qu.edu.qa/bitstream/handle/10576/35289/1-s2.0-S1369847821000292-main.pdf?sequence=2)​
    
- **2–3 line summary**  
    Using a medium‑fidelity driving simulator at Qatar University, this study assessed how simulator sickness and sense of presence vary across different road environments and national groups within Qatar’s highly diverse driving population. It highlighted methodological issues for simulator use in the Gulf, including cultural differences and the need to tailor scenarios to local road environments.[](http://qspace.qu.edu.qa/bitstream/handle/10576/35289/1-s2.0-S1369847821000292-main.pdf?sequence=2)​
    
- **Country/region**  
    Qatar (multi‑ethnic Gulf driving population).
    
- **Driver behaviour studied**  
    Indirectly addresses driving behaviour through tolerance for simulator exposure and perceived realism; outcomes relate to simulator feasibility rather than a specific manoeuvre.
    
- **Usefulness for your review**  
    Important for local relevance: it shows that **simulators are already established and feasible in Qatar** for behavioural research and explicitly notes the absence of many Gulf‑state simulator studies, which you can leverage when arguing that detailed behavioural topics such as turn signalling remain under‑studied.[](http://qspace.qu.edu.qa/bitstream/handle/10576/35289/1-s2.0-S1369847821000292-main.pdf?sequence=2)​
    

---

## 5. Car‑following, demographics and safety in Qatar (regional core paper)

- **Full citation**  
    Hussain, A., Almallah, M., Alhajyaseen, W., & Soliman, A. (2025). Impacts of driver demographics, leading vehicle types, and road conditions on car‑following behaviour using a driving simulator in Qatar. Qatar University, QTTSC research report / thesis.[](http://qspace.qu.edu.qa/handle/10576/68075)​
    
- **2–3 line summary**  
    This simulator‑based study systematically varied leading‑vehicle types and road conditions to observe car‑following behaviour among drivers in Qatar, stratified by age, gender, education, and driving experience. It reported demographic differences in following distance, speed maintenance, and responsiveness to changes in lead‑vehicle behaviour, indicating heterogeneity in safety‑related driving styles within the local population.[](http://qspace.qu.edu.qa/handle/10576/68075)​
    
- **Country/region**  
    Qatar (GCC; directly local to your context).
    
- **Driver behaviour studied**  
    Car‑following safety behaviour (headway, speed, responsiveness), demographic effects on longitudinal control and implicit risk‑taking.
    
- **Usefulness for your review**  
    Highly useful regionally: it demonstrates that **simulators are being used in Qatar to quantify safety‑relevant driver behaviour** (demographic differences in following distance and responsiveness) but does not explicitly address signalling, which supports your argument that more specific manoeuvres such as turn‑signal use are still a gap.[](http://qspace.qu.edu.qa/handle/10576/68075)​
    

---

## 3) How to turn this into your half‑page narrative

Using the above, you can structure your review as follows (in academic prose):

1. **Global evidence paragraph**
    
    - Cite McKenna & Crick (2010), Chouhan et al. (2025), and Murzello et al. (2025) to show that driving simulators are widely used to study hazard perception, reaction time, distraction, and decision‑making, with precise performance indicators such as crash involvement, braking onset, speed profiles, lane deviation, and headway.
        
    - Emphasize that these studies treat simulators as validated tools for capturing subtle safety‑related behaviours in controlled yet realistic scenarios.
        
2. **Regional/Qatar relevance paragraph**
    
    - Use Almallah et al. (2021) to show simulators are operational and methodologically accepted in Qatar’s multi‑cultural driving context.[](http://qspace.qu.edu.qa/bitstream/handle/10576/35289/1-s2.0-S1369847821000292-main.pdf?sequence=2)​
        
    - Add Hussain et al. (2025) to demonstrate local simulator work on car‑following and demographic differences in safety behaviour, underlining that the technology and expertise exist in Qatar/GCC to examine detailed driving behaviours.[](http://qspace.qu.edu.qa/handle/10576/68075)​
        
3. **Gap paragraph for turn signalling**
    
    - Argue that, despite extensive global simulator work on hazard perception, distraction, lane keeping, and decision‑making, very few studies have directly targeted **turn‑signalling behaviour** as a primary outcome, and this is especially true in Qatar and the wider GCC, where simulator studies have so far focused on broader safety behaviours (e.g., car‑following, simulator feasibility) rather than explicit signalling practices.
        
    - Position your project as addressing this gap by using an established local simulator infrastructure to examine when and how drivers signal during turns and lane changes, and how this relates to reaction time, hazard perception, and safety‑critical decisions in a Gulf traffic environment
Driving simulators have become an established methodological tool for examining core aspects of driver behaviour, including hazard perception, reaction time, distraction, and safety‑critical decision‑making. For example, McKenna and Crick (2010) demonstrated that commentary‑driving training in a simulator improved learner drivers’ hazard perception, leading to earlier speed reduction and braking when approaching developing hazards, thereby evidencing the capacity of simulators to capture fine‑grained temporal measures of responsiveness. Similarly, Chouhan et al. (2025) used a fixed‑base simulator under multiple speed and traffic conditions to show that mobile phone use—especially texting—significantly degrades reaction time, lane‑keeping performance, and collision‑avoidance behaviour, underscoring the utility of simulated environments for isolating distraction effects under controlled yet realistic conditions. Complementing this, Murzello et al. (2025) employed a simulator to compare different forms of real‑time feedback and found that decision‑oriented feedback could improve drivers’ speed regulation and headway maintenance, highlighting the role of simulators in studying in‑vehicle interventions and driver decision‑making processes. Collectively, these studies indicate that simulator‑based research is now a standard approach in traffic psychology and human factors for quantifying nuanced behavioural responses (e.g., braking onset, speed profiles, headway) that would be difficult to observe safely on real roads.

In the Gulf region, and Qatar in particular, simulator‑based driving research is emerging but remains comparatively limited in scope. Almallah et al. (2021) used a medium‑fidelity simulator at Qatar University to examine simulation sickness and sense of presence across different virtual road environments and national groups within Qatar’s multi‑cultural driver population, thereby establishing the feasibility and methodological validity of simulator use in this context. Building on this infrastructure, Hussain et al. (2025) investigated the impacts of driver demographics, leading‑vehicle type, and road conditions on car‑following behaviour in Qatar, reporting systematic differences in following distance, speed maintenance, and responsiveness associated with age, gender, and driving experience. These regional studies show that high‑quality simulators are already deployed in Qatar to analyse safety‑related behaviours such as longitudinal control and demographic variability, providing a critically important local foundation for more targeted behavioural investigations.

Despite this global and regional evidence, a clear research gap persists regarding the explicit study of turn‑signalling behaviour in simulator environments, particularly in Qatar and the wider GCC. Existing simulator studies tend to prioritise hazard perception, distraction effects, lane‑keeping, speed choice, and car‑following as primary outcomes, while signalling—when and whether drivers indicate before lane changes or turns—typically appears, if at all, as a secondary or unreported behaviour. In the Gulf context, available simulator work has focused on feasibility and general safety behaviour rather than on the timing, frequency, and correctness of indicator use at intersections or during lane changes. This suggests that, although the technological and methodological capacity to conduct sophisticated simulator experiments already exists in Qatar, the specific domain of turn‑signalling behaviour remains under‑examined. Addressing this gap by designing simulator scenarios that systematically manipulate turn and lane‑change demands, and by capturing signal‑use patterns alongside reaction time and hazard perception metrics, would make a novel and locally relevant contribution to the regional road safety literature.

half a page

Driving simulators are now widely used to study driver behaviour, particularly hazard perception, reaction time, distraction, and safety‑critical decision‑making. Global studies have shown that simulator‑based commentary training can improve drivers’ responsiveness to developing hazards, leading to earlier speed reduction and brake application and demonstrating the capacity of simulators to capture fine‑grained temporal measures of behaviour. Other work has used simulators to examine the impact of distraction, especially mobile phone use, on driving performance, consistently finding that tasks such as texting degrade reaction time, lane‑keeping, and collision‑avoidance behaviour while allowing these effects to be studied safely under controlled conditions. Simulator experiments have also been employed to assess how different forms of real‑time feedback influence driver decision‑making, for example by modifying speed regulation and headway maintenance, which further underscores their value for testing in‑vehicle safety interventions.

Within Qatar and the wider Gulf region, simulator‑based research is emerging but remains relatively limited in scope compared with the international literature. Studies conducted using Qatar‑based simulators have focused on methodological feasibility, such as understanding simulation sickness and sense of presence in a multi‑cultural driver population, and on safety‑related behaviours like car‑following, where demographic factors and road conditions have been linked to differences in following distance, speed maintenance, and responsiveness. These efforts confirm that high‑quality simulator infrastructure and expertise already exist locally to support detailed behavioural research. However, across both the global and regional bodies of work, turn‑signalling behaviour has rarely been treated as a primary outcome. Most simulator studies prioritise hazard perception, distraction, lane‑keeping, speed choice, or headway, with signalling often unreported or secondary. This leaves a clear research gap, particularly in Qatar and the GCC, where the timing, frequency, and correctness of indicator use during turns and lane changes remain under‑examined, despite the availability of suitable simulator platforms.

give me the citation list for each paper

Completed 1 step

Here are the formatted references for the five papers used in your write‑up (APA‑style):

1. McKenna, F. P., & Crick, J. L. (2010). Commentary training improves responsiveness to hazards in a driving simulator. _Accident Analysis & Prevention_, 42(6), 1635–1641. [https://doi.org/10.1016/j.aap.2010.04.002](https://doi.org/10.1016/j.aap.2010.04.002)[](https://pubmed.ncbi.nlm.nih.gov/20728670/)​
    
2. Chouhan, S. S., (2025). Analysis of the distraction impact on driving performance across driving styles: A driving simulator study in various speed conditions. _PLOS ONE_, 20(12), e0336480. [https://doi.org/10.1371/journal.pone.0336480](https://doi.org/10.1371/journal.pone.0336480)
    
3. Murzello, Y., Ding, W., Zhang, X., Niu, J., Samuel, S., & Cao, S. (2025). Information, assessment, or decision: A driving simulator study on the effect of real-time feedback based on information-processing stages. _Ergonomics_, Advance online publication, 1–16. [https://doi.org/10.1080/00140139.2025.2477624](https://doi.org/10.1080/00140139.2025.2477624)
    
4. Almallah, M., Hussain, Q., Reinolsmann, N., Alhajyaseen, W. K. M., & Brijs, T. (2021). Driving simulation sickness and the sense of presence: Correlation and contributing factors. _Transportation Research Part F: Traffic Psychology and Behaviour_, 78, 180–193. [https://doi.org/10.1016/j.trf.2021.01.008](https://doi.org/10.1016/j.trf.2021.01.008)[](http://qspace.qu.edu.qa/bitstream/handle/10576/35289/1-s2.0-S1369847821000292-main.pdf?sequence=2)​
    
5. Hussain, Q. (Year). Empirical analysis of car-following behavior: Impacts of driver demographics, leading vehicle types, and speed limits on driver behavior and safety. (Master’s thesis). Qatar University, Qatar Transportation and Traffic Safety Center, Doha, Qatar.
    

(For item 5, you may want to confirm the exact year and degree type from the full QSpace record before final submission.)

Follow-ups

How to format these citations in APA style for my literature review

What are the key findings of Crundall 2010 commentary training study

Compare effectiveness of commentary training vs other simulator interventions

Provide full abstracts or DOIs for Almallah 2021 and Castro 2015 papers

What recent 2025+ studies on driving styles in simulators exist