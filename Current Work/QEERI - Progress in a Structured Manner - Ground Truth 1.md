==Overall Approach== - Materials Informatics
1. Dataset has to be prepared -> Establish a OTE Dataset just like Taylor Sparks {sysTEM}
	1. Dataset has to include [Structure, Characterization, Property, Processing, Performance]
2. Predict new OTE Structures/Property using Physics informed machine learning tasks
Learn: [Materials informatics, Machine Learning, Physics Informed Machine Learning, Data Mining]
===============================================================



===============================================================
**Learn Notes:**
1. ==Machine Learning==
2. ==Materials Informatics== - Use data + Machine Learning + Materials Science to **discover** or **optimize** materials faster
	1.  Taylor sparks playlist put it into gpt
3. ==Physics Informed Machine Learning==
	1. Frameworks - {input format, model design, loss function, training method, physics constraints}
		1. **PINN** - {Boundary conditions, initial conditions, governing equations, forward (known cause -> unknown effect) vs inverse problem ( known effect -> unknown cause }
		2. Neural Operators
	2. **Three main ways to embed physics into machine learning models**
		1. Add physics through the data
		2. Add physics through the model architecture - {GNN}![[Pasted image 20260503232514.png]]
		3. Add physics through the loss function
		4. Adding physics during inference
	3. **Types of physics knowledge**
		1. Differential equations -> {ODEs, PDEs, SDEs} - PIML tries to satisfy these equations
		2. Symmetry and invariance -> PIML should respect patterns under transformations
		3. Conservation laws
		4. Intuitive physics - common sense physics, balls fall due to gravity {hard to write as equations but help the model understand physical reality
	4. Pytorch Implementation
4. ==Data Mining==
	1. 


===============================================================
**Resources:**

===============================================================
**Important Advice:**
1. Inverse Problems: We can identify unknown material properties like thermal conductivity by fitting the model to limited observed data
2. Simple PINN Code Walkthrough: https://www.youtube.com/watch?v=1qyZaTF-MUQ
3. Materials can be treated as graphs, look into Graph Neural Networks