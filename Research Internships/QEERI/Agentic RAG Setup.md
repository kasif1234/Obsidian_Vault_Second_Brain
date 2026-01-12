==Dai Haiwen's Approach + Agentic RAG Architecture==

>==**Section 1: Target Data Types**== -> Defines _what_ scientific information must be extracted, spanning performance metrics, experimental setup, catalyst preparation, and multimodal characterization.  The focus is on ensuring complete catalyst-to-performance traceability, including difficult non-textual sources such as curves and plots.
>**==Section 2: Data Schema Specification**== -> Formalizes _how_ the extracted information is structured, normalized, and stored using a consistent schema. This section ensures comparability across studies by standardizing fields, units, defaults, and conditional parameters.
> ==**Section 3: Implementation Plan**== -> Outlines _how_ the extraction pipeline is developed, validated, and scaled using a ==Golden-to-Silver dataset strategy==.  The goal is to iteratively refine a reliable multimodal pipeline and then scale it efficiently while maintaining accuracy comparable to large models. [Scientifically conservative, Methodologically sound, Publication-ready] - Silver is unseen data, u use it for validation if refinement of validation improves golden dataset then accept the new checkpoint

![[Pasted image 20260108081653.png]]

## How to keep this publishable (no hallucination)
In your dataset, store **two layers**:
1. **Extracted points** (from Graph2Table)
    - with figure ID, page, method = “digitized”(Graph2Table)
2. **Reconstructed points** (interpolated/fitted)
    - with method = “interpolated” or “fitted”
    - plus the fitting method and parameters