## Evaluation of Idea 2: "The Elemental AI Table by Discovery Timeline"

**Strengths.** This is the most intellectually ambitious of the five ideas because it maps most faithfully onto the actual chemistry periodic table — the one people remember from school. By assigning atomic numbers based on discovery chronology, it tells the *story* of AI as a field, which gives it an educational and narrative power the other ideas lack. The group/family columns (Statistical Foundations, Neural Architectures, etc.) create the same "elements in the same column share deep properties" insight that makes the real periodic table so elegant — alkali metals all react with water, and similarly, all Generative Models share a latent-space-to-output-space mapping. The "periods as complexity layers" concept (single neurons at the top, trillion-parameter systems at the bottom) mirrors the real table's progression from simple to complex atoms. The "radioactive/unstable" markers for powerful-but-unpredictable techniques add visual intrigue and genuine informational value. This is the version most likely to go viral as an educational poster and most likely to be adopted by university courses.

**Weaknesses.** Chronological ordering creates awkward placement decisions. Many techniques were developed gradually rather than "discovered" at a discrete moment — attention mechanisms evolved across multiple papers from 2014–2017 before crystallizing in the Transformer. Forcing a single atomic number onto fuzzy timelines invites pedantic objections. The group/family metaphor also strains at the edges: in chemistry, group membership is determined by electron configuration, a deep structural property. In AI, the boundaries between "Classical ML" and "Statistical Foundations" or between "Generative Models" and "Neural Architectures" are debatable and overlapping — a VAE is both a generative model and a neural architecture. The complexity-as-periods mapping is also imperfect because some simple techniques (like k-nearest neighbors) remain highly effective at scale, and some complex architectures (like certain GNN variants) operate on small data. Finally, the chemistry-faithful layout limits how many elements you can include before the table becomes visually overwhelming — the real table has 118 elements and already feels dense.

**Mitigations.** Use the "discovery date" as a rough anchor rather than a precise claim — group elements into eras (1940s–1960s, 1980s–1990s, 2010s, 2020s) and assign atomic numbers within eras by influence rather than exact publication date. Acknowledge that group boundaries are interpretive, not structural, and use color gradients rather than hard lines between adjacent families. Add a "lanthanide/actinide" overflow strip for elements that don't fit cleanly, just as the real table does.

**Verdict.** This is the highest-ceiling idea for education, storytelling, and virality. It rewards deep study — people will spend time tracing lineages and debating placements, which is engagement gold. But it also demands the most curatorial judgment and will attract the most criticism for any perceived misplacement. Worth building for an audience that values intellectual depth and historical context: researchers, students, AI historians, and science communicators.

---

## Detailed Version: The Elemental AI Periodic Table

### Structural Principles

The table follows the chemistry periodic table's core logic as closely as possible.

**Atomic Number (Z):** Assigned chronologically by the foundational publication or moment of broad adoption. Where a technique evolved over multiple papers, the number anchors to the most influential single work. Numbers run from 1 (earliest) to ~100+ (frontier research circa 2026). The number conveys *historical sequence*, not importance.

**Groups (Vertical Columns):** Eight groups representing fundamental *families* of AI concepts that share deep structural or philosophical kinship — analogous to how elements in the same chemical group share valence electron behavior. Elements in the same group, regardless of when they were discovered, share a core operational principle.

**Periods (Horizontal Rows):** Seven periods representing increasing *complexity and capability*, from simple single-component techniques at the top to massive compound systems at the bottom. This mirrors chemistry's progression from hydrogen (Period 1) to oganesson (Period 7).

**Element Tile Format:**
```
┌────────────────────┐
│ 27            Tf    │
│   Transformer       │
│   2017 · Vaswani    │
│  ● ● ● ● ○  [4/5]  │
│  NEURAL ARCH        │
└────────────────────┘
```
Top-left: atomic number. Top-right: 1–3 letter symbol. Center: full name. Below: year and key author/lab. Dots: current influence rating (1–5 filled circles). Bottom: group label. Color: determined by group.

**Radioactive/Unstable Marker (☢):** Applied to elements that are powerful but carry significant unpredictability, safety concerns, or unresolved failure modes. Analogous to radioactive elements in chemistry — useful but requiring careful containment.

**Lanthanide/Actinide Strips:** Two overflow rows at the bottom for elements that span multiple groups or represent cross-cutting mathematical/theoretical foundations that underpin many families without belonging to a single one.

---

### Group I — STATISTICAL FOUNDATIONS (Slate Blue)
*The noble gases of AI — stable, well-understood, and foundational to everything else.*

| Z | Sym | Element | Year | Key Origin | Influence |
|---|---|---|---|---|---|
| 1 | **By** | Bayes' Theorem | 1763 | Bayes / Laplace | ●●●●● |
| 2 | **Rg** | Linear Regression | 1805 | Legendre / Gauss | ●●●●● |
| 5 | **Mc** | Markov Chains | 1906 | Markov | ●●●●○ |
| 9 | **It** | Information Theory | 1948 | Shannon | ●●●●● |
| 14 | **Nb** | Naïve Bayes | 1960s | Various | ●●●○○ |
| 22 | **Em** | EM Algorithm | 1977 | Dempster, Laird, Rubin | ●●●●○ |
| 30 | **Mc** | MCMC Methods | 1953/1990s | Metropolis / Geman | ●●●○○ |
| 55 | **Cs** | Causal Inference | 2000s | Pearl | ●●●●○ |

---

### Group II — CLASSICAL ML (Forest Green)
*Workhorses that dominated before deep learning and remain indispensable.*

| Z | Sym | Element | Year | Key Origin | Influence |
|---|---|---|---|---|---|
| 3 | **Kn** | k-Nearest Neighbors | 1951 | Fix & Hodges | ●●●○○ |
| 7 | **Pc** | Perceptron | 1958 | Rosenblatt | ●●●●○ |
| 12 | **Dt** | Decision Trees | 1963 | Morgan & Sonquist | ●●●●○ |
| 18 | **Sv** | Support Vector Machine | 1992 | Boser, Guyon, Vapnik | ●●●○○ |
| 20 | **Rf** | Random Forest | 2001 | Breiman | ●●●●○ |
| 24 | **Gb** | Gradient Boosting | 1999 | Friedman | ●●●●● |
| 34 | **Xg** | XGBoost | 2014 | Chen & Guestrin | ●●●●● |
| 46 | **Km** | K-Means Clustering | 1957 | Lloyd | ●●●○○ |

---

### Group III — NEURAL ARCHITECTURES (Deep Purple)
*The structural blueprints of connectionist AI — how artificial neurons are wired together.*

| Z | Sym | Element | Year | Key Origin | Influence |
|---|---|---|---|---|---|
| 8 | **Ml** | Multilayer Perceptron | 1960s | Various | ●●●○○ |
| 10 | **Bp** | Backpropagation | 1986 | Rumelhart, Hinton, Williams | ●●●●● |
| 13 | **Cn** | Convolutional Neural Net | 1989 | LeCun | ●●●●● |
| 16 | **Ls** | LSTM | 1997 | Hochreiter & Schmidhuber | ●●●●○ |
| 21 | **Ae** | Autoencoder | 1986/2006 | Rumelhart / Hinton | ●●●○○ |
| 27 | **Tf** | Transformer | 2017 | Vaswani et al. | ●●●●● |
| 33 | **Gn** | Graph Neural Network | 2005/2017 | Gori / Kipf & Welling | ●●●○○ |
| 42 | **Mx** | Mixture of Experts | 1991/2022 | Jacobs / Fedus | ●●●●○ |
| 50 | **Ss** | State-Space Models | 2021 | Gu et al. (S4 / Mamba) | ●●●○○ |

---

### Group IV — OPTIMIZATION & TRAINING (Amber)
*The alchemical fire — techniques that turn architecture + data into learned capability.*

| Z | Sym | Element | Year | Key Origin | Influence |
|---|---|---|---|---|---|
| 4 | **Gd** | Gradient Descent | 1847 | Cauchy | ●●●●● |
| 11 | **Sg** | Stochastic Gradient Descent | 1951/1986 | Robbins & Monro / Rumelhart | ●●●●● |
| 19 | **Do** | Dropout | 2012 | Hinton et al. | ●●●●○ |
| 23 | **Bn** | Batch Normalization | 2015 | Ioffe & Szegedy | ●●●●○ |
| 26 | **Ad** | Adam Optimizer | 2014 | Kingma & Ba | ●●●●● |
| 35 | **Wp** | Warmup & LR Scheduling | 2017 | Vaswani et al. / Smith | ●●●●○ |
| 41 | **Lo** | LoRA | 2021 | Hu et al. | ●●●●○ |
| 48 | **Ds** | Distillation | 2015 | Hinton, Vinyals, Dean | ●●●●○ |
| 56 | **Qz** | Quantization | 2015+ | Various | ●●●●○ |

---

### Group V — GENERATIVE MODELS (Crimson)
*Elements that create — producing new text, images, audio, video, and code from learned distributions.*

| Z | Sym | Element | Year | Key Origin | Influence |
|---|---|---|---|---|---|
| 15 | **Hm** | Hidden Markov Model | 1966 | Baum & Petrie | ●●○○○ |
| 25 | **Ga** | GAN | 2014 | Goodfellow et al. | ●●●●○ |
| 28 | **Va** | VAE | 2013 | Kingma & Welling | ●●●○○ |
| 31 | **Gp** | GPT (Autoregressive LM) | 2018 | Radford / OpenAI | ●●●●● |
| 36 | **Br** | BERT (Masked LM) | 2018 | Devlin / Google | ●●●●○ |
| 39 | **Df** | Diffusion Models | 2020 | Ho et al. | ●●●●● |
| 44 | **Fl** | Flow Matching | 2022 | Lipman et al. | ●●●○○ |
| 52 | **Vc** | Video Generation | 2024 | Sora / various | ●●●○○ ☢ |
| 58 | **Wm** | World Models | 2018/2024 | Ha & Schmidhuber / LeCun | ●●○○○ ☢ |

---

### Group VI — REINFORCEMENT LEARNING (Emerald)
*Learning through interaction — agents that maximize cumulative reward via trial and experience.*

| Z | Sym | Element | Year | Key Origin | Influence |
|---|---|---|---|---|---|
| 6 | **Td** | Temporal Difference | 1988 | Sutton | ●●●●○ |
| 17 | **Ql** | Q-Learning | 1989 | Watkins | ●●●●○ |
| 29 | **Dq** | Deep Q-Network | 2013 | Mnih / DeepMind | ●●●●○ |
| 32 | **Pg** | Policy Gradient | 1992/2015 | Williams / Schulman (PPO) | ●●●●● |
| 37 | **Ag** | AlphaGo / AlphaZero | 2016 | Silver / DeepMind | ●●●●○ |
| 43 | **Rh** | RLHF | 2017/2022 | Christiano / Ouyang | ●●●●● |
| 51 | **Dp** | DPO (Direct Preference) | 2023 | Rafailov et al. | ●●●●○ |
| 57 | **Ma** | Multi-Agent RL | 2017+ | Various | ●●●○○ ☢ |

---

### Group VII — MULTIMODAL & RETRIEVAL SYSTEMS (Coral)
*Elements that bridge modalities, connect models to external knowledge, and fuse information streams.*

| Z | Sym | Element | Year | Key Origin | Influence |
|---|---|---|---|---|---|
| 38 | **Cl** | CLIP | 2021 | Radford / OpenAI | ●●●●● |
| 40 | **Rg** | RAG | 2020 | Lewis et al. / Meta | ●●●●● |
| 45 | **Vs** | Vector Search | 2010s/2023 | Various (FAISS, etc.) | ●●●●○ |
| 47 | **Wh** | Whisper (Speech→Text) | 2022 | Radford / OpenAI | ●●●●○ |
| 49 | **Vl** | Vision-Language Models | 2023+ | GPT-4V, Gemini, Claude | ●●●●● |
| 53 | **Fc** | Function Calling | 2023 | OpenAI / Anthropic | ●●●●○ |
| 59 | **Sf** | Sensor Fusion | 2000s+ | Autonomous vehicles, robotics | ●●●○○ |

---

### Group VIII — EMERGENT CAPABILITIES & FRONTIER (Gold)
*The transuranic elements of AI — recently synthesized, intensely studied, often unstable. Many carry the ☢ marker.*

| Z | Sym | Element | Year | Key Origin | Influence |
|---|---|---|---|---|---|
| 54 | **Ic** | In-Context Learning | 2020 | Brown et al. (GPT-3) | ●●●●● |
| 60 | **Co** | Chain-of-Thought | 2022 | Wei et al. / Google | ●●●●● |
| 62 | **Tk** | Tool Use | 2023 | Schick (Toolformer) / various | ●●●●○ |
| 64 | **Aa** | Autonomous Agents | 2023 | AutoGPT, Voyager, various | ●●●○○ ☢ |
| 66 | **Sc** | Scaling Laws | 2020 | Kaplan et al. / Hoffmann (Chinchilla) | ●●●●● |
| 68 | **Ct** | Constitutional AI | 2022 | Bai et al. / Anthropic | ●●●●○ |
| 70 | **Lm** | Long Context (1M+ tokens) | 2024 | Gemini, Claude, various | ●●●●○ |
| 72 | **Rs** | Reasoning Models | 2024 | o1, Claude extended thinking | ●●●●○ ☢ |
| 74 | **Si** | Self-Improvement ☢ | Theoretical | — | ●○○○○ ☢ |

---

### LANTHANIDE STRIP — Mathematical & Theoretical Foundations
*Cross-cutting mathematical bedrock that underpins multiple groups, placed below the main grid.*

| Z | Sym | Element | Year | Note |
|---|---|---|---|---|
| L1 | **La** | Linear Algebra | — | Vectors, matrices, tensor operations — the language of all neural computation |
| L2 | **Pr** | Probability Theory | — | Distributions, sampling, likelihood — the grammar of uncertainty |
| L3 | **Cl** | Calculus / Autodiff | — | Derivatives, chain rule — the engine of backpropagation |
| L4 | **Op** | Convex Optimization | — | Constraint satisfaction, convergence guarantees for classical methods |
| L5 | **Gt** | Game Theory | — | Equilibria, adversarial dynamics — foundational to GANs and multi-agent systems |
| L6 | **Ct** | Category Theory | — | Compositional structure — emerging theoretical lens for neural network design |
| L7 | **Cx** | Complexity Theory | — | Computational hardness, NP problems — theoretical limits of what's learnable |

---

### ACTINIDE STRIP — Infrastructure & Ecosystem
*The heavy industrial substrate that makes modern AI physically possible.*

| Z | Sym | Element | Year | Note |
|---|---|---|---|---|
| A1 | **Gp** | GPU Computing | 2007+ | NVIDIA CUDA and massively parallel hardware acceleration |
| A2 | **Tp** | TPU / Custom Silicon | 2016+ | Google TPUs, AWS Trainium, specialized AI accelerators |
| A3 | **Pt** | PyTorch | 2016 | Dominant research framework with eager execution |
| A4 | **Jx** | JAX | 2018 | Google's composable transformations framework (grad, jit, vmap) |
| A5 | **Hf** | HuggingFace Ecosystem | 2018+ | Model hub, datasets, tokenizers — the package manager of ML |
| A6 | **Dc** | Data Commons | 2010s+ | Common Crawl, The Pile, LAION — large-scale public training corpora |
| A7 | **Cl** | Cloud ML Platforms | 2015+ | AWS SageMaker, GCP Vertex, Azure ML — managed training and serving |

---

### Period Mapping (Horizontal Rows)

| Period | Complexity Level | Characteristic | Chemistry Analogy |
|---|---|---|---|
| **1** | Single-component | Individual statistical methods, one-variable models | Hydrogen, Helium |
| **2** | Simple compositions | Basic classifiers, shallow nets, single-layer systems | Li → Ne |
| **3** | Multi-layer systems | Deep networks, ensemble methods, multi-step pipelines | Na → Ar |
| **4** | Large-scale trained | Pre-trained models, large corpora, GPU clusters required | K → Kr |
| **5** | Billion-parameter | LLMs, large diffusion models, RLHF-tuned systems | Rb → Xe |
| **6** | Frontier systems | Multimodal, agent-based, long-context, reasoning chains | Cs → Rn |
| **7** | Theoretical/speculative | Self-improving systems, artificial general intelligence | Fr → Og |

---

### Reading the Table — Interpretive Keys

**Color coding** works on two axes simultaneously. The primary hue comes from the Group (column family) — Statistical is slate blue, Classical ML is green, Neural Architectures is purple, and so on. A secondary saturation gradient runs top-to-bottom by Period: lighter tints at the top (simple, well-understood) deepening to rich saturated tones at the bottom (complex, frontier).

**The ☢ Radioactive Marker** appears on elements that meet at least two of three criteria: (1) capable of producing outputs humans struggle to distinguish from reality, (2) exhibiting emergent behaviors not explicitly programmed, (3) lacking robust interpretability or containment guarantees. It's not a judgment of the element's value — radioactive elements in chemistry are enormously useful — but a flag that extra care is warranted.

**"Predicted Elements" (dashed borders):** Just as Mendeleev left gaps for undiscovered elements and predicted their properties, this table includes 3–5 tiles with dashed borders and question marks representing capabilities the field is converging toward but hasn't achieved: true continuous learning without catastrophic forgetting, grounded common-sense reasoning, energy-efficient neuromorphic AI, and provably safe autonomous agents. Their approximate positions in the grid signal which group and complexity level the community expects them to inhabit.

**Isotopes (small superscript notation):** Some elements have meaningful variants. For example, Transformer²⁷ might carry superscripts for Encoder-only (BERT-style), Decoder-only (GPT-style), and Encoder-Decoder (T5-style). This keeps the main grid clean while acknowledging important sub-variants for practitioners who want to go deeper.

---

### Visual & Design Notes

The poster uses a landscape 36"×24" format. The main grid occupies the upper two-thirds. The Lanthanide and Actinide strips sit in a separated band across the lower third, connected to the main grid by reference arrows (matching the chemistry convention of pulling rows 6–7's f-block elements out to avoid an unmanageably wide table). A timeline ruler runs along the top edge, mapping atomic numbers to decades. A legend in the bottom-right explains the tile anatomy, the ☢ marker criteria, the influence rating scale, and the predicted-element dashed borders. The reverse side of the poster (or a companion digital interactive version) contains a one-paragraph deep-dive on each element with key paper citations, making it both a wall reference and a self-study curriculum.
