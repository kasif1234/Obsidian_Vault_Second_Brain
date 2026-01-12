![[Pasted image 20260105103423.png]]
[[AI&ML_Overview.canvas|AI&ML_Overview]]

==
==Overview==:
- Define problem
    
- Collect data
    
- Clean data
    
- Represent data
    
- Split data
    
- Choose model
    
- Train
    
- Evaluate
    
- Deploy
    
- Monitor
In Depth:
## . Problem Definition (the most skipped step)

**Without this**  
You optimize the wrong thing perfectly.

**Key questions**

- What is the input?
    
- What is the output?
    
- Is this classification, regression, ranking, generation?
    
- What error is unacceptable?
    

**Output**

- Clear task definition
    
- Success metric
    
- Constraints (latency, accuracy, cost)
    

---

## 2. Data Collection

**Without care**  
The model learns the wrong world.

**Sources**

- Sensors, logs, databases
    
- Images, text, audio, video
    
- Human annotations
    

**Output**

- Raw dataset
    
- Metadata (source, time, conditions)
    

---

## 3. Data Cleaning & Preprocessing

![https://framerusercontent.com/images/W45Na0PeEKPJVt5dk35aML4gj98.png?height=1232&width=1240](https://framerusercontent.com/images/W45Na0PeEKPJVt5dk35aML4gj98.png?height=1232&width=1240)

![https://cdn.analyticsvidhya.com/wp-content/uploads/2025/07/image4-15.webp](https://cdn.analyticsvidhya.com/wp-content/uploads/2025/07/image4-15.webp)

![https://ashutoshtripathi.com/wp-content/uploads/2021/06/image-3.png](https://ashutoshtripathi.com/wp-content/uploads/2021/06/image-3.png)

**Problem**  
Raw data is messy, inconsistent, incomplete.

**Typical steps**

- Remove duplicates
    
- Handle missing values
    
- Normalize / standardize
    
- Resize images, tokenize text
    

**Output**

- Clean, usable data
    

---

## 4. Feature Engineering (or Representation Learning)

**Old ML**

- Hand-crafted features
    

**Modern ML**

- Neural networks learn features automatically
    

**Examples**

- Text → embeddings
    
- Images → feature maps
    
- Time series → windows
    

**Output**

- Numerical representations the model can learn from
    

---

## 5. Train / Validation / Test Split

**Why**  
To measure generalization, not memorization.

**Typical split**

- Train: learn
    
- Validation: tune
    
- Test: final evaluation
    

**Rule**  
Test set is sacred. Never tune on it.

---

## 6. Model Selection

![https://dezyre.gumlet.io/images/blog/model-selection-in-machine-learning/Model_Evaluation_and_Selection_in_Data_Mining.png?dpr=2.6&w=376](https://dezyre.gumlet.io/images/blog/model-selection-in-machine-learning/Model_Evaluation_and_Selection_in_Data_Mining.png?dpr=2.6&w=376)

![https://media.geeksforgeeks.org/wp-content/uploads/20240923112128/Machine-learning-vs-neural-networks.webp](https://media.geeksforgeeks.org/wp-content/uploads/20240923112128/Machine-learning-vs-neural-networks.webp)

![https://media.licdn.com/dms/image/v2/C4D12AQGK6ZI-GBwgag/article-cover_image-shrink_600_2000/article-cover_image-shrink_600_2000/0/1530142591985?e=2147483647&t=1xwoJgHc5x4OiPnlVw2MWMZTZnfF98tK6LrLf6EcHRA&v=beta](https://media.licdn.com/dms/image/v2/C4D12AQGK6ZI-GBwgag/article-cover_image-shrink_600_2000/article-cover_image-shrink_600_2000/0/1530142591985?e=2147483647&t=1xwoJgHc5x4OiPnlVw2MWMZTZnfF98tK6LrLf6EcHRA&v=beta)

**Choices**

- Linear models
    
- Tree-based models
    
- Neural networks
    
- Transformers
    

**Decision depends on**

- Data size
    
- Data type
    
- Constraints
    

**Output**

- Chosen architecture
    

---

## 7. Training

**What happens**

- Model makes predictions
    
- Loss measures error
    
- Optimizer updates weights
    

**Key elements**

- Loss function
    
- Optimizer
    
- Learning rate
    
- Batch size
    

**Output**

- Trained model weights
    

---

## 8. Evaluation

![https://miro.medium.com/v2/resize%3Afit%3A1400/1%2A8VM2PELQ-oeM0O3ya7BIyQ.png](https://miro.medium.com/v2/resize%3Afit%3A1400/1%2A8VM2PELQ-oeM0O3ya7BIyQ.png)

![https://www.dataschool.io/content/images/2015/01/confusion_matrix_simple2.png](https://www.dataschool.io/content/images/2015/01/confusion_matrix_simple2.png)

![https://miro.medium.com/1%2AaBdOAvzxIuVPWB7qZVZogA.png](https://miro.medium.com/1%2AaBdOAvzxIuVPWB7qZVZogA.png)

**Why**  
Accuracy alone lies.

**Metrics**

- Classification: precision, recall, F1
    
- Regression: MAE, RMSE
    
- Segmentation: IoU, Dice
    

**Also check**

- Failure cases
    
- Bias
    
- Stability
    

---

## 9. Deployment

![https://christophergs.com/assets/images/deployment.png](https://christophergs.com/assets/images/deployment.png)

![https://cdn.prod.website-files.com/618399cd49d125734c8dec95/66a3437f014c1e1ac78d4e04_6502adf3ca2eceb7be5b949e_figure%25206_lightbox.png](https://cdn.prod.website-files.com/618399cd49d125734c8dec95/66a3437f014c1e1ac78d4e04_6502adf3ca2eceb7be5b949e_figure%25206_lightbox.png)

![https://www.cardinalpeak.com/wp-content/uploads/2021/12/cloud-ai-vs-edge-ai-blog-figure2.png](https://www.cardinalpeak.com/wp-content/uploads/2021/12/cloud-ai-vs-edge-ai-blog-figure2.png)

**Forms**

- API
    
- Edge device
    
- Batch inference
    

**Constraints**

- Latency
    
- Memory
    
- Throughput
    

**Output**

- Model in production
    

---

## 10. Monitoring & Feedback Loop

**Reality**  
The world changes.

**Monitor**

- Input drift
    
- Performance decay
    
- Unexpected failures
    

**Action**

- Retrain
    
- Update data
    
- Adjust model
    

**This closes the loop.**

====
Paper -> ==Machine learning for molecular and materials science==
## 1. The old world: physics-first, slow, expensive

Traditionally, chemistry and materials science worked like this:

- Start from **first principles physics** (Schrödinger equation)
    
- Use **quantum mechanics (DFT)** to compute properties
    
- This gives very accurate results
    
- But it is **slow**, **expensive**, and **does not scale well**
    

Even with supercomputers:

- You can simulate thousands of materials, not millions
    
- You usually ask _forward questions_:  
    “Given this structure, what property does it have?”
    

This is called **first- and second-generation computational chemistry**.

---

## 2. The core insight: structure → property is learnable

The authors point out something crucial:

> If structure determines properties, and we already have large datasets of structures and properties, then **a machine can learn this mapping directly**.

So instead of:

- Solving Schrödinger’s equation every time
    

You can:

- Learn a statistical approximation of it
    
- Once learned, predictions are **instant**
    

This does **not replace physics**, but **compresses it into a model**.

---

## 3. What machine learning changes fundamentally

Machine learning introduces **three major shifts**:

### (a) From equations → data-driven rules

Instead of hard-coded physics:

- Models **learn patterns** from data
    
- Can discover correlations humans did not encode explicitly
    

### (b) From forward prediction → inverse design

Instead of asking:

- “What is the property of this material?”
    

You can ask:

- “What material should I make to get this property?”
    

This is huge.  
It turns science from **analysis** into **design**.

### (c) From isolated steps → closed-loop discovery

Machine learning can connect:

- synthesis
    
- characterization
    
- simulation
    
- decision-making
    

into a **feedback loop** that improves itself.

---

## 4. The generic ML workflow they want you to understand

Every successful ML application in chemistry follows this pipeline:

1. **Data collection**
    
    - experiments
        
    - simulations (DFT)
        
    - databases
        
2. **Representation**
    
    - turn molecules/crystals into numbers or graphs
        
    - this step is critical and non-trivial
        
3. **Learning**
    
    - supervised (most common)
        
    - unsupervised (patterns, clustering)
        
    - semi-supervised (limited labels)
        
4. **Model selection and validation**
    
    - bias vs variance
        
    - cross-validation
        
    - testing on unseen data
        

This pipeline is **the backbone of modern materials informatics**.

---

## 5. What do ML models actually predict?

The paper is very clear that **there is no single output**.  
Depending on the task, ML predicts:

- **Properties**  
    band gap, formation energy, conductivity, toxicity, activity
    
- **Structures**  
    which crystal structure a composition will adopt
    
- **Synthesis decisions**  
    reaction routes, reaction conditions, likelihood of crystallization
    
- **New compounds**  
    molecules or materials that do not yet exist
    
- **Next experiments**  
    active learning tells you what to try next
    

So ML is not one tool, but a **family of tools**.

---

## 6. Where ML already works well

The paper highlights strong successes in:

- High-throughput materials screening
    
- Drug discovery (QSAR, deep learning)
    
- Neural network potentials replacing force fields
    
- Retrosynthesis planning
    
- Literature mining and knowledge extraction
    

In these areas, ML is **already outperforming traditional workflows**.

---

## 7. Where ML still struggles

The authors are honest about limitations:

- **Small datasets** (chemistry data is expensive)
    
- **Representation problems** (especially for crystals)
    
- **Generalization** outside training distribution
    
- **Interpretability** (black-box models)
    
- **Error propagation** across multi-scale models
    

These are not minor issues.  
They are **active research problems**.

---

## 8. The future vision (this is the punchline)

The paper envisions a future where:

- ML models act as **surrogate physical laws**
    
- Discovery becomes **statistically driven**
    
- Experiments are **machine-guided**
    
- New principles may be discovered by machines
    
- Quantum computing may accelerate both physics and ML
    

In short:

> Science shifts from “derive → test → repeat”  
> to “learn → predict → design → verify”