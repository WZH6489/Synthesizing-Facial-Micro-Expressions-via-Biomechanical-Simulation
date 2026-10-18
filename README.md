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
Results + Stiffness / Damping Findings
```

---

# 🔬 Method

1. **Isolate** one muscle activation at a time so each effect on the skin can be attributed to a single cause.
2. **Simulate** a sweep of low-amplitude activations and record the skin motion.
3. **Collect reference footage** of the matching real facial movement (see [Reference Footage](#-reference-footage)).
4. **Compare** simulation and reference visually (side-by-side, overlays) and numerically (strain, displacement; see [Evaluation Metrics](#-evaluation-metrics)).
5. **Vary material properties** (stiffness, damping) to test whether the pipeline needs different values at smaller scales.
6. **Record** every activation and its result, including failures.

---

# 📊 Results

Simulated micro-expressions for four muscle activations. The videos show the simulation only. The real reference clips come from CASME II and are not redistributed here.

| Action unit | Emotion label | Simulation |
| ----------- | ------------- | ---------- |
| AU1         | Surprise      | [Watch](assets/videos/au1_surprise_sim.mp4) |
| AU12        | Happiness     | [Watch](assets/videos/au12_happiness_sim.mp4) |
| AU15        | Repression    | [Watch](assets/videos/au15_repression_sim.mp4) |
| AU20        | Fear          | [Watch](assets/videos/au20_fear_sim.mp4) |

**Main finding:** _TBD: does the pipeline natively handle micro-expressions, or does it need different material stiffness/damping at smaller scales?_

---

# 📈 Evaluation Metrics

Simulated micro-expressions are compared against real human reference footage with:

- **Visual comparison:** side-by-side and overlay of the simulated skin motion with the reference footage
- **Strain:** local deformation of the skin surface in simulation versus reference
- **Displacement:** skin or landmark displacement in simulation versus reference (state units: pixels or mm)
- **Native vs. adjusted properties:** whether the pipeline reproduces the reference with its current settings, or only after changing material stiffness and damping at smaller scales

---

# 🧱 Repository Structure

```
Synthesizing-Facial-Micro-Expressions-via-Biomechanical-Simulation/
│
├── README.md
├── LICENSE
│
├── assets/
│   └── videos/              # simulated micro-expression videos
│
└── data/
    └── README.md            # reference footage notes (data not stored in Git)
```

Reference footage, Maya scenes and the lab facial model are not stored in this repository.

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

# 🛠 Technologies

- Python
- Autodesk Maya
- Maya Commands (cmds)
- Biomechanical Simulation
- Muscle Activation Control
- Computer Vision
- Strain and Displacement Analysis

---

# 🚀 Future Work

**Project 2: Synthesizing Fine-Grained Facial Dynamics: Micro-Expressions and Indigenous Phonemes** is the planned continuation of this project.

- Synthesize the phonetic inventories of Canadian Indigenous languages (such as Coast Salish or Hul'q'umi'num'), which demand specific lip-rounding and facial tension for ejective sounds
- Simulate involuntary micro-expressions, such as repressed smiles and fleeting brow furrows, by injecting asymmetric, high-frequency, low-duration muscle bursts into the pipeline
- Isolate the motor unit activations required for these complex movements
- Test whether the physical parameters capture distinct skin, lip and jaw dynamics without losing structural volume
- Measure temporal strain distribution and jaw displacement against real human footage
- Evaluate whether the simulation natively handles high-frequency articulatory movements or requires novel co-activation strategies
- Build a documented asset library of muscle activation parameters for these fine-grained movements

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

This project is conducted as part of an undergraduate research position at Simon Fraser University.

Supervised by **Zhiyun (Richard) Peng** and **Eugene Fiume** at the **GrUVi Lab**, School of Computing Science, Simon Fraser University.
