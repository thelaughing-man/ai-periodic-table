## Evaluation of Idea 3: "The AI Capability Maturity Table"

**Strengths.** This is the most *accessible* of the five ideas because it's organized around what AI can do rather than how it works. That distinction matters enormously for audience reach. Ideas 1 and 2 speak to practitioners and researchers; Idea 3 speaks to everyone who *uses* or *buys* AI — product managers, executives, investors, policymakers, journalists, and curious non-technical people. The capability-centric framing also makes the table naturally forward-looking: instead of cataloging historical techniques, it maps the frontier of what's possible, what's nearly possible, and what remains out of reach. The "Undiscovered Elements" zone is the single most compelling design feature across all five ideas — it directly invokes Mendeleev's most famous contribution (predicting gallium, germanium, and scandium before they were found) and reframes the AI field as a landscape with known blanks. This creates conversation: people will debate what belongs in those empty slots, which drives engagement. The maturity scoring system (1–5 instead of importance weights) also avoids the subjectivity problem of Idea 1's weights — "how solved is this?" is more empirically grounded than "how important is this?"

**Weaknesses.** The biggest structural challenge is that capabilities don't have the clean mutual exclusivity that chemical elements do. "Summarization" is a capability, but it's also a sub-capability of "Understanding," and it draws on "Memory & Retrieval" when applied to long documents, and it overlaps with "Generation" because producing a summary is a generative act. The SEO Periodic Table and the chemistry table both benefit from elements that are conceptually atomic — hydrogen is not a sub-type of carbon. AI capabilities nest, overlap, and compose in ways that make clean categorization genuinely hard. If the table doesn't handle this well, it will feel arbitrary. A second weakness is the maturity score's shelf life: AI capabilities advance rapidly, and a score of "2/5" for video understanding in early 2025 might be "4/5" by late 2026. The table would need versioning or a dynamic digital format to stay credible. Third, there's a risk of the table reading as a product marketing matrix rather than a scientific reference — "what can AI do for you?" tilts toward sales deck rather than educational poster.

**Mitigations.** Address the overlap problem by defining capabilities at a consistent level of abstraction — each element should represent a *task family* that a user would recognize as distinct, not a technical sub-component. Use cross-reference indicators (small connector icons) to acknowledge that elements draw on each other without trying to create a strict hierarchy. For the shelf-life problem, design the table with a prominent version date and publish it as an annual snapshot (like the SEO table's 2-year update cycle). For the marketing-deck risk, include the "Undiscovered" and "Emerging" zones prominently — a sales deck never admits what it *can't* do, so the honest inclusion of unsolved problems signals intellectual seriousness.

**Verdict.** This is the best idea for maximum audience breadth and cultural impact. It's the version a newspaper would print, a VC would frame, and a congressional staffer would reference. It sacrifices technical depth for conceptual clarity and trades precision for resonance. Worth building as the "public-facing" companion to Idea 1's "practitioner-facing" table — they serve complementary audiences and could even be published as a pair.

---

## Detailed Version: The AI Capability Maturity Table

### Structural Principles

The table organizes AI not by technique or history but by *what the technology can do from a human's perspective*. It answers the question: "If I wanted AI to help me with X, how mature is that capability today?"

**Category Columns:** Eight capability families, arranged left-to-right by a rough progression from *perceiving* the world, to *understanding* it, to *reasoning* about it, to *creating* new things, to *acting* in it. This mirrors a loose cognitive arc without claiming AI is cognitive.

**Maturity Score (M):** Each element carries a score from 1 to 5 representing how reliably and broadly the capability works today, across leading systems, in real-world conditions (not cherry-picked demos).

| Score | Label | Meaning |
|---|---|---|
| **M5** | **Solved** | Superhuman or reliably human-level in production across domains. Commoditized. |
| **M4** | **Strong** | Works well in most contexts with occasional failures. Deployed at scale. |
| **M3** | **Emerging** | Impressive demos, works in constrained settings, but brittle or inconsistent at the edges. |
| **M2** | **Early** | Active research frontier. Promising results in papers, but not reliable in production. |
| **M1** | **Nascent** | Theoretical or proof-of-concept only. The community agrees it matters, but no one has cracked it. |

**Undiscovered Elements (dashed borders, no score):** Capabilities the field believes *should* exist — or will need to exist — but that no current system demonstrates even at M1. These are the table's most provocative and discussion-worthy entries.

**Element Tile Format:**
```
┌─────────────────────┐
│ M4            Tr     │
│   Translation        │
│   ─────────────────  │
│   ████████░░  [4/5]  │
│   UNDERSTANDING      │
└─────────────────────┘
```
Top-left: maturity score. Top-right: 1–3 letter symbol. Center: capability name. Below: filled progress bar visualizing the maturity score. Bottom: category label. A small arrow icon (↑↗→) indicates the *velocity* of improvement — is this capability advancing rapidly (↑), steadily (↗), or plateauing (→)?

**Cross-Reference Connectors:** Small colored dots in the bottom-right corner of a tile indicate which other categories the capability draws on. For example, "Code Generation" in the Generation column might carry a small Reasoning dot and a small Understanding dot, signaling that it depends on capabilities from those families. This addresses the overlap problem without breaking the grid.

---

### Category 1 — PERCEPTION (Sky Blue)
*Sensing and recognizing patterns in raw input — the AI equivalent of eyes, ears, and touch.*

| M | Sym | Capability | Velocity | Description |
|---|---|---|---|---|
| M5 | **Ir** | Image Recognition | → | Identifying objects, scenes, and faces in photographs. Superhuman on standard benchmarks, fully commoditized. |
| M5 | **Sr** | Speech Recognition | → | Converting spoken audio into text across major languages. Production-grade in noisy environments. |
| M4 | **Od** | Object Detection | ↗ | Localizing and labeling multiple objects within images/video in real time. Robust for common objects, weaker on rare categories. |
| M4 | **Or** | OCR & Document Parsing | ↗ | Extracting structured text from scanned documents, receipts, handwriting. Strong for typed text, improving for messy handwriting. |
| M3 | **Av** | Audio Understanding | ↑ | Classifying non-speech sounds: music genre, environmental audio, emotional tone in voice. Advancing rapidly with multimodal models. |
| M3 | **Vu** | Video Understanding | ↑ | Comprehending temporal sequences: actions, events, narratives across video frames. Impressive recent progress but still struggles with long-form and causal sequences. |
| M3 | **3d** | 3D Scene Perception | ↗ | Reconstructing and understanding three-dimensional environments from 2D inputs (NeRFs, Gaussian splatting, depth estimation). |
| M2 | **Tc** | Tactile / Haptic Sensing | ↗ | Interpreting physical contact, texture, and pressure — critical for robotics manipulation. Hardware-limited. |
| M1 | **Ol** | Olfactory / Chemical Sensing | → | AI-driven smell and taste recognition. Largely theoretical with limited sensor hardware. |

---

### Category 2 — UNDERSTANDING (Teal)
*Extracting meaning, structure, and relationships from perceived input — comprehension beyond pattern matching.*

| M | Sym | Capability | Velocity | Description |
|---|---|---|---|---|
| M5 | **Tr** | Translation | → | Converting text between major language pairs at professional quality. Near-solved for high-resource languages, weaker for low-resource. |
| M4 | **Sm** | Summarization | ↗ | Condensing long documents into shorter faithful representations. Strong for news and reports, less reliable for highly technical or nuanced material. |
| M4 | **Sa** | Sentiment & Tone Analysis | → | Detecting emotional valence, sarcasm, urgency, and intent in text. Production-grade for common use cases. |
| M4 | **Ie** | Information Extraction | ↗ | Pulling structured data (entities, relationships, events) from unstructured text. Strong with LLM-based approaches. |
| M3 | **Dc** | Document Comprehension | ↑ | Answering complex questions that require synthesizing information across long, multi-section documents. Improving rapidly with extended context windows. |
| M3 | **Mu** | Multimodal Understanding | ↑ | Jointly reasoning over text, images, charts, and audio within a single input. The fastest-moving element on the table. |
| M2 | **Pm** | Pragmatic / Implicit Meaning | ↗ | Grasping what's implied but unsaid — reading between the lines, understanding social context, detecting subtext. |
| M2 | **Nu** | Numerical Reasoning in Text | ↗ | Reliably performing arithmetic, unit conversion, and quantitative comparison embedded in natural language contexts. |
| M1 | **Sr** | Sarcasm & Deep Irony | → | Reliably detecting layered irony, cultural in-jokes, and context-dependent humor across cultures. |

---

### Category 3 — REASONING (Indigo)
*Drawing inferences, solving problems, and constructing logical chains — the "thinking" capabilities.*

| M | Sym | Capability | Velocity | Description |
|---|---|---|---|---|
| M4 | **Lg** | Logical Deduction | ↑ | Following explicit logical rules: if A then B, syllogisms, constraint satisfaction. Strong with chain-of-thought prompting, but still trips on adversarial edge cases. |
| M4 | **Mt** | Mathematical Problem Solving | ↑ | Solving textbook-to-competition-level math problems. Rapid improvement via reasoning models (o1, extended thinking), but unreliable on novel proof construction. |
| M3 | **Pl** | Planning & Decomposition | ↑ | Breaking complex goals into ordered sub-tasks and anticipating dependencies. Works for well-defined domains, struggles with open-ended or ambiguous goals. |
| M3 | **An** | Analogical Reasoning | ↗ | Identifying structural parallels between different domains ("this is like that"). Emerging capability in large models, inconsistent. |
| M3 | **Sp** | Spatial Reasoning | ↗ | Reasoning about physical arrangements, navigation, and geometric relationships from text or image descriptions. |
| M2 | **Cs** | Causal Reasoning | ↗ | Distinguishing cause from correlation, predicting interventional outcomes, constructing causal chains. Active research frontier. |
| M2 | **Ct** | Counterfactual Thinking | ↗ | Reasoning about what *would have* happened under different conditions. Requires robust causal models that current systems mostly lack. |
| M2 | **Ab** | Abstraction & Generalization | ↗ | Extracting general principles from specific examples and applying them to genuinely novel domains. The ARC benchmark frontier. |
| M1 | **Mc** | Meta-Cognition | → | A system's ability to accurately assess what it knows, what it doesn't, and when to seek help. Confidence calibration at a deep level, not surface-level hedging. |

---

### Category 4 — GENERATION (Crimson)
*Producing new content — the creative and productive output capabilities.*

| M | Sym | Capability | Velocity | Description |
|---|---|---|---|---|
| M5 | **Tg** | Text Generation | → | Producing fluent, coherent, stylistically controlled prose across genres. Essentially solved at the fluency level; remaining challenges are factual accuracy and deep creativity. |
| M4 | **Ig** | Image Generation | ↗ | Creating photorealistic or artistic images from text prompts. Strong overall, with remaining challenges in fine-grained control (hands, text in images, precise spatial layouts). |
| M4 | **Cg** | Code Generation | ↑ | Writing, completing, debugging, and explaining software in major programming languages. Rapidly improving; already used daily by millions of developers. |
| M3 | **Ag** | Audio / Music Generation | ↑ | Creating music, sound effects, and voice from text descriptions or melodies. Quality improving fast, but coherence over long compositions and stylistic control remain challenges. |
| M3 | **Vg** | Video Generation | ↑ | Producing short video clips from text or image prompts. Visually impressive but physically inconsistent and limited in duration and controllability. |
| M3 | **Dg** | Data / Synthetic Data Generation | ↗ | Creating realistic tabular data, simulated environments, and training examples. Useful for augmentation, but fidelity to real distributions varies. |
| M3 | **3g** | 3D Asset Generation | ↑ | Creating meshes, textures, and 3D scenes from text or images. Rapid recent progress but not yet production-grade for high-fidelity applications. |
| M2 | **Sg** | Scientific Hypothesis Generation | ↗ | Proposing novel, testable scientific hypotheses by synthesizing existing literature. Early promising results (AlphaFold-adjacent work), far from reliable autonomous discovery. |
| M2 | **Ng** | Narrative / Long-Form Storytelling | ↗ | Generating novel-length fiction with sustained character development, thematic coherence, and structural arcs. Current systems lose coherence beyond a few thousand words. |

---

### Category 5 — MEMORY & RETRIEVAL (Amber)
*Storing, finding, and connecting information across time and space — AI's relationship with knowledge.*

| M | Sym | Capability | Velocity | Description |
|---|---|---|---|---|
| M4 | **Se** | Semantic Search | ↗ | Finding information by meaning rather than keyword match. Production-grade via embedding models and vector databases. |
| M4 | **Rg** | Retrieval-Augmented Generation | ↑ | Grounding model outputs in retrieved external documents to reduce hallucination and ensure currency. Widely deployed, improving in precision. |
| M4 | **Lc** | Long Context Processing | ↑ | Ingesting and reasoning over very long inputs (100K–2M tokens). Available in frontier models; reliability degrades with "needle in a haystack" tasks at extreme lengths. |
| M3 | **Kn** | Knowledge Graph Integration | ↗ | Combining structured knowledge graphs with neural models for more reliable factual reasoning. |
| M2 | **Cm** | Conversational Memory | ↑ | Maintaining coherent, personalized context across multiple sessions over weeks or months. Early implementations exist, but robust long-term memory with appropriate forgetting remains unsolved. |
| M2 | **Ep** | Episodic Memory | ↗ | Storing and retrieving specific past experiences (not just facts) and using them to inform future behavior. Largely a research concept. |
| M1 | **Cl** | Continuous Learning | → | Accumulating new knowledge over time without catastrophic forgetting and without full retraining. The holy grail of lifelong learning; no system does this reliably. |

---

### Category 6 — INTERACTION (Green)
*How AI engages with humans, tools, and environments — the interface capabilities.*

| M | Sym | Capability | Velocity | Description |
|---|---|---|---|---|
| M5 | **Ch** | Conversational Chat | → | Multi-turn dialogue that maintains context, follows instructions, and adapts tone. The core interface of modern LLMs, essentially commoditized. |
| M4 | **Tu** | Tool Use / Function Calling | ↑ | Invoking external APIs, databases, calculators, and services based on natural language requests. Deployed widely, improving in reliability and chaining. |
| M4 | **If** | Instruction Following | ↗ | Precisely executing complex, multi-constraint natural language instructions. Strong for clear directives, weaker for ambiguous or contradictory requirements. |
| M3 | **Aa** | Autonomous Agents | ↑ | Systems that independently plan, execute multi-step tasks, recover from errors, and manage sub-goals with minimal human oversight. The hottest frontier in applied AI. |
| M3 | **Co** | Collaborative Co-creation | ↑ | Working alongside a human in a shared creative or analytical process with turn-taking, feedback incorporation, and initiative. |
| M2 | **Em** | Embodied Interaction | ↗ | Controlling a physical robot body to manipulate objects, navigate spaces, and interact with the physical world based on language commands. |
| M2 | **Ng** | Negotiation & Persuasion | ↗ | Engaging in goal-directed dialogue where the AI has objectives (scheduling, deal-making, conflict resolution) and must navigate competing interests. |
| M1 | **Tp** | Theory of Mind | → | Modeling another agent's (human or AI) beliefs, knowledge, and intentions to predict behavior and adapt accordingly. Debated whether current systems exhibit any genuine version of this. |

---

### Category 7 — JUDGMENT & TRUST (Gold)
*Capabilities related to reliability, self-awareness, and earned trustworthiness — the "should I believe this output?" dimension.*

| M | Sym | Capability | Velocity | Description |
|---|---|---|---|---|
| M4 | **Fc** | Factual Accuracy (with RAG) | ↑ | Producing correct, verifiable claims when grounded in retrieved sources. Strong when sources are available and unambiguous, weaker for synthesized or contested facts. |
| M3 | **Uc** | Uncertainty Communication | ↗ | Expressing appropriate confidence levels — saying "I'm not sure" when it genuinely isn't, rather than hedging everything or asserting everything. |
| M3 | **Ex** | Explainability | ↗ | Providing human-understandable justifications for why a particular output was produced. Surface-level explanations (chain-of-thought) are strong; deep mechanistic explanations remain limited. |
| M3 | **Bi** | Bias Detection & Mitigation | ↗ | Identifying and reducing systematic unfairness in outputs across demographic groups. Progress in measurement tools, but mitigation without performance trade-offs is unsolved. |
| M2 | **Vr** | Self-Verification | ↑ | Checking its own outputs for errors, inconsistencies, and hallucinations before presenting them. Emerging via critic models and self-reflection prompting. |
| M2 | **Sf** | Safety Refusal Calibration | ↑ | Correctly refusing genuinely harmful requests while not over-refusing benign ones. Threading the needle between helpful and safe remains an active challenge. |
| M2 | **Pr** | Provenance Tracking | ↗ | Attributing specific claims to specific sources with verifiable citations, enabling end-users to audit the output. |
| M1 | **Cr** | Corrigibility | → | A system's willingness to be corrected, shut down, or redirected by authorized humans, even when its internal objectives might resist. A core alignment research concept. |

---

### Category 8 — AUTONOMY & AGENCY (Slate)
*Capabilities related to independent goal pursuit, self-direction, and operating without human guidance — the most frontier and most contested territory.*

| M | Sym | Capability | Velocity | Description |
|---|---|---|---|---|
| M3 | **Gd** | Goal Decomposition | ↑ | Breaking a high-level objective into executable sub-goals without human hand-holding. Works for well-scoped tasks, unreliable for open-ended ones. |
| M3 | **Er** | Error Recovery | ↑ | Detecting when an action has failed and autonomously trying an alternative approach. Current agents can retry and adapt in narrow loops. |
| M2 | **Lp** | Long-Horizon Planning | ↗ | Maintaining coherent pursuit of a goal across dozens or hundreds of steps over hours or days. Current agents degrade significantly beyond ~15–20 steps. |
| M2 | **Rm** | Resource Management | ↗ | Deciding how to allocate limited budgets — compute, API calls, tokens, time, money — in pursuit of a goal. |
| M2 | **Dl** | Delegation | ↗ | An AI system recognizing when a sub-task is better handled by another model, tool, or human, and routing accordingly. |
| M1 | **Ad** | Self-Directed Learning | → | Autonomously identifying knowledge gaps, seeking out new information or training data, and improving without human-initiated retraining cycles. |
| M1 | **Vl** | Value Alignment Under Ambiguity | → | Making judgment calls in novel situations where instructions don't clearly apply, in ways that reliably reflect the principal's values. The deepest unsolved alignment problem. |

---

### UNDISCOVERED ELEMENTS — The Empty Slots

These are the Mendeleev gaps — capabilities the community anticipates but no system demonstrates, even at M1. They appear on the table as dashed-border tiles with "?" symbols, positioned in the category column where they'd logically belong. Their presence is the table's most important intellectual claim: *we know the map has blank spots, and naming them focuses research attention.*

| Sym | Predicted Capability | Expected Category | Why It Matters |
|---|---|---|---|
| **?1** | **True Common Sense** | Reasoning | The ability to make the millions of obvious inferences humans take for granted ("if you drop an egg, it breaks") without being explicitly taught each one. The Winograd / Cyc dream. |
| **?2** | **Lossless Lifelong Learning** | Memory & Retrieval | Accumulating unbounded new knowledge and skills continuously without forgetting old ones and without full retraining. Currently unsolved at any scale. |
| **?3** | **Cross-Domain Creative Transfer** | Generation | Applying creative insight from one domain (e.g., jazz improvisation) to a structurally analogous problem in an unrelated domain (e.g., protein folding). Humans call this "genius-level analogy." |
| **?4** | **Genuine Surprise & Curiosity** | Autonomy & Agency | An intrinsic drive to explore, question, and seek novelty — not because a reward signal incentivizes it, but as an emergent epistemic motivation. The bridge to open-ended learning. |
| **?5** | **Cultural & Contextual Fluency** | Understanding | Deep, intuitive grasp of culturally specific meanings, social norms, power dynamics, and unwritten rules across thousands of human subcultures. Current models have surface-level cultural knowledge. |
| **?6** | **Robust Physical Intuition** | Reasoning | Reliable intuitive physics — predicting how objects move, break, flow, and interact in the real world without running an explicit simulation. Critical for robotics and embodied AI. |
| **?7** | **Autonomous Ethical Reasoning** | Judgment & Trust | The ability to identify, analyze, and navigate novel ethical dilemmas without falling back on rigid rules or deferring every edge case to a human. Philosophically and technically the hardest predicted element. |

---

### Reading the Table — Interpretive Keys

**The Maturity Progress Bar** in each tile provides instant visual scanning. A reader can glance across the table and immediately see the topography of what's solved (full bars, left side of the table) versus what's frontier (mostly-empty bars, right side). This creates a natural left-to-right "maturity gradient" that visually communicates the field's overall shape.

**Velocity Arrows (↑ ↗ →)** add a critical temporal dimension that static maturity scores miss. An element at M2↑ (early but advancing rapidly) tells a very different story than M2→ (early and stalled). For investors and strategists, the velocity is arguably more important than the current score — it signals where the breakthroughs are likely to come next.

**Cross-Reference Dots** appear as small colored circles (matching category colors) in the lower-right corner of each tile. Code Generation, for instance, carries Reasoning (indigo) and Understanding (teal) dots, signaling that its maturity is partly gated by progress in those adjacent families. This helps readers understand *dependency chains* — why some capabilities can't advance until others do.

**The Undiscovered Zone** sits below the main grid in a distinct visual band with a muted, blueprint-style aesthetic (dashed lines, lighter colors). Its placement and styling are deliberately reminiscent of the blank spaces in Mendeleev's 1869 table — a visual assertion that the field knows its own boundaries and is honest about them.

---

### Versioning & Lifecycle

Unlike the chemistry periodic table (which changes slowly as new elements are synthesized), this table is designed to be re-evaluated annually. Each annual edition carries a version date (e.g., "AI Capability Table — March 2026 Edition") and a change log highlighting which elements shifted maturity scores, which moved velocity categories, and whether any Undiscovered Elements were promoted to M1. Over time, the archived editions become a visual record of the field's progress — a time-lapse of AI maturation that no single paper or benchmark can provide.

---

### Visual & Design Notes

The table uses a portrait 24"×36" poster format optimized for office and classroom walls. Category columns are arranged in a gentle arc rather than a strict grid, subtly evoking a capability "landscape" from perception on the left to autonomy on the right. Each column's header includes a simple icon (an eye for Perception, a lightbulb for Reasoning, a paintbrush for Generation, etc.) for instant recognition. The Undiscovered Elements band runs across the full bottom width with a distinct blueprint/wireframe aesthetic. A companion interactive web version allows filtering by maturity score, velocity, and category, with expandable tiles that link to key papers, products, and benchmarks for each element. The poster's footer includes a QR code linking to the interactive version and an invitation: *"Which element do you think will shift first? Tell us at [URL]."*
