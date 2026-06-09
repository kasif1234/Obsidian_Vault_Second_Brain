==Overall Approach== - Materials Informatics
1. Dataset has to be prepared -> Establish a OTE Dataset just like Taylor Sparks {sysTEM}
	1. Dataset has to include [Structure, Characterization, Property, Processing, Performance]
2. Frame the paper as a contribution to existing databases, ==[you found one already]==
3. Predict new OTE Structures/Property using Physics informed machine learning tasks
Learn: [Materials informatics, Machine Learning, Physics Informed Machine Learning, Data Mining, EDA]


Holistic Overview Diagram -> https://drive.google.com/file/d/1jChlm9JlYiQVdJdfqKAhJUeNlzKKNIO0/view?usp=sharing

===============================================================

==Meeting Updates: - (12/05/2026)==
Add these to the metadata list
- publishing group 
- journal name
30 main materials science journals
Frame the paper with existing dbs
Each journal related to QU, Texas, HBKU -> ethical reasons


===============================================================
**Learn Notes:**
1. ==Machine Learning==
2. ==Materials Informatics== - Use data + Machine Learning + Materials Science to **discover** or **optimize** materials faster
	1.  Taylor sparks playlist put it into GPT
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
4. ==Data Mining
	1. ==
5.  ==EDA==: 
	1.  Here are three primary types of EDA: **univariate (analysing one variable), bivariate (comparing two variables), and multivariate (investigating relationships between three or more variables)**.


===============================================================
**Resources:**

===============================================================
**Important Advice:**
1. Inverse Problems: We can identify unknown material properties like thermal conductivity by fitting the model to limited observed data
2. Simple PINN Code Walkthrough: https://www.youtube.com/watch?v=1qyZaTF-MUQ
3. Materials can be treated as graphs, look into Graph Neural Networks



===============================================================
==**Dataset Structure**==
# 1. Molecular design

**Meaning:** Changing the polymer’s chemical structure so charge carriers move better and thermoelectric properties improve.

| Parameter                           | Definition / why it matters                                                                                                                                      |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Polymer backbone structure**      | The main conjugated chain; a more ordered and conjugated backbone improves charge transport.                                                                     |
| **Conjugation length**              | Longer conjugation allows charges to move more easily along the polymer chain.                                                                                   |
| **Side-chain length**               | Controls packing, dopant access, solubility, and polymer ordering.                                                                                               |
| **Side-chain polarity**             | Polar side chains can improve dopant mixing and reduce dopant clustering.                                                                                        |
| **HOMO/LUMO energy levels**         | Determines whether the polymer works better as p-type or n-type and whether dopants match well.                                                                  |
| **Band gap**                        | Smaller or optimized band gaps usually help charge generation and transport.                                                                                     |
| **Fermi level / density of states** | Controls the Seebeck coefficient and carrier transport behavior.                                                                                                 |
| **Intrinsic polymer flexibility**   | Important for wearable thermoelectric devices.                                                                                                                   |
| **Environmental stability**         | A stable polymer keeps performance under air, heat, and humidity.                                                                                                |
| **SMILES**                          | SMILES is a text representation of the chemical structure, so it describes the polymer’s backbone, side chains, conjugation, heteroatoms, and functional groups. |

---

# 2. Doping

**Meaning:** Adding dopants to increase useful charge carriers and improve electrical conductivity.

|Parameter|Definition / why it matters|
|---|---|
|**Dopant type**|The chemical dopant used; it must match the polymer energy levels for good charge transfer.|
|**Doping level**|Amount of dopant added; too little gives low conductivity, too much can damage morphology.|
|**Doping efficiency**|How many useful charge carriers are created per dopant molecule.|
|**Carrier concentration**|Number of electrons or holes; must be optimized because too much can reduce Seebeck coefficient.|
|**p-type / n-type behavior**|Shows whether holes or electrons are the main charge carriers.|
|**Charge-transfer strength**|Measures how effectively the dopant gives or removes electrons from the polymer.|
|**Dopant dispersion**|Uniform dopant distribution gives better and more stable conductivity.|
|**Dopant-polymer miscibility**|Good mixing prevents phase separation and improves performance.|

The paper explains that doping and molecular ordering are major ways to improve conjugated polymer thermoelectric performance.

---

# 3. Transport decoupling

**Meaning:** Improving electrical transport without increasing heat transport too much.

|Parameter|Definition / why it matters|
|---|---|
|**Seebeck coefficient, S**|Voltage generated from a temperature difference; higher is better.|
|**Electrical conductivity, σ**|Ability to conduct current; higher is better.|
|**Thermal conductivity, κ**|Ability to conduct heat; lower is usually better for thermoelectrics.|
|**Power factor, PF = S²σ**|A key performance metric, especially for organic polymers.|
|**ZT = S²σT/κ**|Overall thermoelectric efficiency metric.|
|**Carrier mobility**|How easily carriers move; higher mobility improves electrical conductivity.|
|**Electron/phonon transport balance**|Charges should move easily, but heat vibrations should be blocked.|
|**Nanostructuring**|Can scatter phonons and reduce thermal conductivity without strongly hurting electrical conductivity.|
|**Interfacial thermal resistance**|Interfaces can block heat flow and help keep κ low.|
|**Temperature gradient, ΔT**|Bigger temperature difference gives larger thermoelectric voltage.|

The paper says improving ZT is difficult because SSS, σ\sigmaσ, and κ\kappaκ are interdependent, so better materials need decoupling strategies.

---

# 4. Morphology control

**Meaning:** Controlling the physical arrangement of polymer chains, crystals, domains, and films.

|Parameter|Definition / why it matters|
|---|---|
|**π–π stacking**|Close stacking between conjugated chains helps charge hopping.|
|**Chain alignment**|Aligned polymer chains give easier charge transport in one direction.|
|**Crystallinity / order**|More order can improve mobility, but too much order may block dopant diffusion.|
|**Film morphology**|Smooth, connected, ordered films improve charge transport.|
|**Molecular packing**|Determines how close chains are and how easily charges move.|
|**Phase separation**|Too much separation between polymer and dopant/filler can reduce performance.|
|**Processing method**|Drop-casting, spin coating, rubbing, printing, etc. affect final morphology.|
|**Film thickness**|Affects conductivity, heat transfer, and device performance.|
|**Contact resistance**|Poor contact between material and electrode wastes generated voltage.|
|**Device geometry**|Leg length, thickness, and area affect output voltage and power.|

The paper specifically notes that chain alignment, structural order, and close intermolecular contact improve electrical conductivity in organic thermoelectric polymers.

---

# 5. Hybrid composites

**Meaning:** Mixing organic polymers with conductive or thermoelectric fillers to improve transport pathways.

|Parameter|Definition / why it matters|
|---|---|
|**Filler type**|CNTs, graphene, Bi₂Te₃, SnSe, Bi₂Se₃, etc. can improve electrical/thermoelectric performance.|
|**Filler loading**|Amount of filler; too little gives weak pathways, too much can reduce flexibility or Seebeck coefficient.|
|**Filler dispersion**|Uniform filler distribution prevents weak regions and improves transport.|
|**Filler network connectivity**|A continuous network creates better electrical pathways.|
|**Polymer-filler interface**|Strong interfaces improve charge transfer between polymer and filler.|
|**Interfacial compatibility**|Good chemical/physical matching prevents aggregation and poor transport.|
|**Percolation threshold**|Minimum filler amount needed to form a connected conductive network.|
|**Hybrid p-type/n-type design**|Needed to build full thermoelectric generators with both legs.|
|**Mechanical flexibility of composite**|Composite should still bend or stretch for wearable applications.|

The paper says hybrid organic thermoelectrics use the low thermal conductivity of polymers and the high electrical conductivity of inorganic fillers to improve performance.

---

## Clean dataset version

For your dataset, you can organize columns like this:

| Category                 | Best columns to collect                                                                           |
| ------------------------ | ------------------------------------------------------------------------------------------------- |
| **Molecular design**     | polymer name, polymer family, backbone, side chain, HOMO, LUMO, band gap                          |
| **Doping**               | dopant, dopant concentration, doping method, p-type/n-type, carrier concentration                 |
| **Transport decoupling** | Seebeck coefficient, electrical conductivity, thermal conductivity, power factor, ZT, temperature |
| **Morphology control**   | film method, crystallinity, chain alignment, π–π stacking, thickness, morphology notes            |
| **Hybrid composites**    | filler type, filler loading, filler dispersion, polymer-filler interface, composite structure     |
![[Pasted image 20260515101630.png]]



Bulk Paper Downloading System
│
├── 1. Start With Search Query
│   │
│   └── Purpose:
│       Define what papers you want.
│
│       Example:
│       "organic thermoelectric polymers"
│
│
├── 2. Discover Papers
│   │
│   ├── Crossref
│   │   Purpose: Find DOI, title, authors, journal, publisher, year.
│   │
│   ├── OpenAlex
│   │   Purpose: Find large-scale paper metadata, citations, authors, institutions.
│   │
│   ├── Semantic Scholar
│   │   Purpose: Find related papers, abstracts, citations, open links.
│   │
│   ├── CORE
│   │   Purpose: Find open-access papers and repository links.
│   │
│   ├── Web of Science / Clarivate
│   │   Purpose: Find indexed, high-quality academic records.
│   │
│   └── SerpAPI
│       Purpose: Search the web/Google Scholar-like results using code.
│
│
├── 3. Build Master Paper List
│   │
│   └── Purpose:
│       Combine results from different search tools into one clean list.
│
│       Main fields:
│       DOI
│       Title
│       Authors
│       Journal
│       Publisher
│       Year
│       URL
│
│
├── 4. Remove Duplicates
│   │
│   └── Purpose:
│       Avoid downloading the same paper many times.
│
│       Best duplicate checker:
│       DOI
│
│       If DOI is missing:
│       Use title + authors + year.
│
│
├── 5. Identify Publisher
│   │
│   └── Purpose:
│       Decide which official source owns the paper.
│
│       Examples:
│       Elsevier
│       Springer Nature
│       Wiley
│       IEEE
│       RSC
│       ACS
│       IOP
│       PLOS
│       Taylor & Francis
│
│
├── 6. Check Legal Access
│   │
│   ├── Unpaywall
│   │   Purpose: Check if a legal open-access version exists.
│   │
│   ├── CORE
│   │   Purpose: Check if repository full text is available.
│   │
│   ├── University Library Access
│   │   Purpose: Check if Qatar University gives access.
│   │
│   └── Publisher TDM Policy
│       Purpose: Check if automated downloading/mining is allowed.
│
│
├── 7. Choose Download Route
│   │
│   ├── Open Access Route
│   │   Tools: Unpaywall, CORE, PLOS, PMC
│   │   Purpose: Download legal open-access full text.
│   │
│   ├── Publisher API Route
│   │   Tools: Elsevier, Springer, Wiley, IEEE, RSC, IOP
│   │   Purpose: Download official full text if your key/permission allows it.
│   │
│   ├── Dataset Route
│   │   Tools: CORE Dataset, APS Dataset, TDM Studio
│   │   Purpose: Download papers in bulk from approved datasets.
│   │
│   └── No Permission Route
│       Tools: None
│       Purpose: Skip the paper or record it as unavailable.
│
│
├── 8. Bulk Download Papers
│   │
│   └── Purpose:
│       Download many legal papers automatically.
│
│       Your code should save:
│       PDF
│       XML
│       HTML
│       Supplementary files
│
│
└── 9. Save Download Log
    │
    └── Purpose:
        Track what happened to every paper.
        
        Example statuses:
        Downloaded
        Open access available
        Publisher API success
        No legal access
        Permission required
        Failed download
        Duplicate skipped