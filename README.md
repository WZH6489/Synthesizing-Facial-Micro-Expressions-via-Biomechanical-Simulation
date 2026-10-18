# 🧬 Synthesizing Facial Micro-Expressions via Biomechanical Simulation

**Synthesizing Facial Micro-Expressions via Biomechanical Simulation** is an undergraduate research project at **Simon Fraser University** (GrUVi Lab, School of Computing Science) investigating whether an existing biomechanical facial simulation pipeline can reproduce **micro-expressions**: very subtle, very brief facial movements driven by small muscle activations.

**Goal:** Test if the existing biomechanical pipeline accurately captures microscopic skin dynamics during subtle motor activations.

**Method:** Isolate specific muscle activations and critically evaluate the simulated outputs against real-world reference footage.

The project was carried out from **July to September 2026**.

---

# 🎯 Research Overview

Biomechanical facial models move the skin by simulating the muscles, fat and soft tissue beneath it, rather than deforming the skin surface directly. This makes them attractive for generating realistic facial motion, but the existing pipeline was built and tuned for **large, visible expressions**.

Micro-expressions are different:

- The skin displacements and strains are **tiny**
- The activations are **subtle** and short-lived
- Small errors in the simulation (material properties, damping, numerical noise) can matter as much as the signal itself

This project asks whether the current simulation pipeline **natively handles micro-expressions**, or whether it **requires different material stiffness and damping properties at smaller scales**.

To answer that, individual muscle activations are isolated on the facial model, simulated at low amplitude, and compared against real human reference footage, using both visual inspection and numerical measures such as **strain** and **displacement**.

The work is a **critical evaluation**: documenting where the pipeline fails at micro-scales is as valuable as showing where it succeeds.

---

# 🖼 Pipeline Overview

```
Facial Model (skin, muscles, fat, bone)
        │
        ▼
Select a Single Muscle Activation
        │
        ▼
Apply a Subtle Activation (low-amplitude sweep)
        │
        ▼
Biomechanical Simulation
        │
        ▼
Simulated Micro-Expression
        │
        ▼
Comparison with Real Human Reference Footage
        │
        ▼
Strain / Displacement Analysis (visual + numerical)
        │
        ▼
Asset Library + Stiffness / Damping Findings
```

---

# 📦 Deliverables

- **Asset Library:** A documented database of activation parameters and their corresponding simulated micro-expressions.
- **Analysis:** A visual and numerical comparison (e.g., measuring strain or displacement) between the simulated micro-expressions and real human reference footage.
- **Academic Output:** A short report evaluating whether the current simulation pipeline natively handles micro-expressions or if it requires different material stiffness/damping properties at smaller scales.

| Deliverable     | Location                                       | Status |
| --------------- | ---------------------------------------------- | ------ |
| Asset Library   | [`asset_library/`](asset_library/)             | ☐      |
| Analysis        | [`analysis/`](analysis/)                       | ☐      |
| Academic Output | [`docs/`](docs/)                               | ☐      |

---

# 🔬 Method

1. **Isolate** one muscle activation at a time so each effect on the skin can be attributed to a single cause.
2. **Simulate** a sweep of low-amplitude activations and record the skin motion.
3. **Collect reference footage** of the matching real facial movement (see [Reference Footage](#-reference-footage)).
4. **Compare** simulation and reference visually (side-by-side, overlays) and numerically (strain, displacement; see [Evaluation Metrics](#-evaluation-metrics)).
5. **Vary material properties** (stiffness, damping) to test whether the pipeline needs different values at smaller scales.
6. **Record** every activation and its result in the asset library, including failures.

---

# ✅ Project Status

> Tick these off as the work is finalized.

- [ ] Pipeline set up and verified on the lab facial model
- [ ] Single-muscle isolation workflow documented
- [ ] Activation sweeps simulated
- [ ] Reference footage selected and aligned
- [ ] Visual comparison complete
- [ ] Strain / displacement comparison complete
- [ ] Stiffness and damping experiments complete
- [ ] Asset library documented
- [ ] Short report written

---

# 📊 Results

> Add figures and key findings here, for example a side-by-side of simulated versus real motion for each tested muscle.

```
assets/figures/
```

| Muscle / activation | Amplitude range | Matches reference? | Stiffness / damping change needed? | Notes |
| ------------------- | --------------- | ------------------ | ---------------------------------- | ----- |
| _TBD_               | _TBD_           | _TBD_              | _TBD_                              | _TBD_ |

**Main finding:** _TBD: does the pipeline natively handle micro-expressions, or does it need different material stiffness/damping at smaller scales?_

---

# 📈 Evaluation Metrics

> Trim to what you actually measured.

- **Displacement:** skin or landmark displacement in simulation versus reference (state units: pixels or mm)
- **Strain:** local deformation of the skin surface in simulation versus reference
- **Temporal agreement:** onset, peak and offset timing of the movement
- **Spatial extent:** how far the movement spreads over the face
- **Parameter sensitivity:** how displacement and strain change with activation amplitude, stiffness and damping
- **Visual comparison:** side-by-side and overlay with the reference footage

---

# 📚 Asset Library

The asset library is the main reusable output. Each entry documents one activation: the muscle, the parameter values, the material settings, the simulated result, and how it compares with real footage.

See [`asset_library/`](asset_library/) for the entries and the entry template.

---

# 🧱 Repository Structure

```
Synthesizing-Facial-Micro-Expressions-via-Biomechanical-Simulation/
│
├── README.md
├── LICENSE
├── CITATION.cff
├── requirements.txt
├── .gitignore
│
├── src/                     # Maya / Python scripts for running activations
│
├── asset_library/           # documented activation parameters + simulated micro-expressions
│
├── analysis/                # strain / displacement comparison scripts and notebooks
│
├── data/
│   └── README.md            # reference footage notes (data not stored in Git)
│
├── assets/
│   └── figures/             # figures used in the README and report
│
├── docs/                    # short report and supporting notes
│
└── maya/
    └── README.md            # scene files and plug-in notes
```

Maya scenes (`*.mb`, `*.ma`), raw footage and large renders are ignored by Git.

---

# ⚙️ Setup

Requirements:

- Autodesk Maya with Python 3 (`maya.cmds` ships with Maya)
- The lab biomechanical facial simulation pipeline and facial model scene (not stored in Git)
- Python 3.10 or newer for the analysis scripts (see `requirements.txt`)

```
git clone https://github.com/WZH6489/Synthesizing-Facial-Micro-Expressions-via-Biomechanical-Simulation.git
cd Synthesizing-Facial-Micro-Expressions-via-Biomechanical-Simulation
pip install -r requirements.txt
```

> Add the exact commands for loading the scripts in Maya and running one example activation here.

---

# 🗂 Reference Footage

> Describe the real human reference footage: source, number of clips, frame rate, and how it was aligned with the simulation.

Footage is **not** redistributed in this repository. See [`data/README.md`](data/README.md).

---

# ⚠️ Limitations

> Fill in from your findings. This is part of the academic output.

- Results come from a single facial model.
- _TBD: where the pipeline diverges from real footage at micro-scales._
- _TBD: sensitivity to stiffness, damping and numerical noise at small activations._
- _TBD: limits of the reference footage (resolution, frame rate, lighting) for measuring strain._

---

# 🚀 Future Work

- Extend the evaluation to more muscles and combined activations
- Test on additional facial models and subjects
- Calibrate stiffness and damping automatically for small-scale activations
- Higher-resolution, higher-frame-rate reference capture for more precise strain measurement

---

# 📚 Related Research

This repository accompanies undergraduate research on simulating facial micro-expressions with a biomechanical facial model.

Primary reference:
> **Beneath the Skin: Interactive Biomechanical Facial Simulations via Composable Co-Expressions**

This is the biomechanical facial simulation pipeline whose behavior at micro-scales this project evaluates.

Selected references:

- X. Ben, Y. Ren, J. Zhang, S.-J. Wang, K. Kpalma, W. Meng and Y.-J. Liu, "Video-based facial micro-expression analysis: A survey of datasets, features and algorithms," IEEE Transactions on Pattern Analysis and Machine Intelligence, vol. 44, no. 9, 2022.
- W.-J. Yan, X. Li, S.-J. Wang, G. Zhao, Y.-J. Liu, Y.-H. Chen and X. Fu, "CASME II: An improved spontaneous micro-expression database and the baseline evaluation," PLoS ONE, vol. 9, no. 1, e86041, 2014.
- A. K. Davison, C. Lansley, N. Costen, K. Tan and M. H. Yap, "SAMM: A spontaneous micro-facial movement dataset," IEEE Transactions on Affective Computing, vol. 9, no. 1, pp. 116-129, 2018.

Additional references will be added throughout the project.

---

# 📄 License

This project is released under the MIT License. See the [`LICENSE`](LICENSE) file for details.

Third-party software (such as Autodesk Maya) and any reference footage are covered by their own licenses and are not included.

---

# 👨‍💻 Author

**William Huang**

Project Lead | Undergraduate Researcher
Simon Fraser University

---

# 🙏 Acknowledgements

Supervised by **Zhiyun (Richard) Peng** and **Eugene Fiume** at the **GrUVi Lab**, School of Computing Science, Simon Fraser University.
