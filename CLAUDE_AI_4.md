## Evaluation of Idea 4: "The Full-Stack AI Infrastructure Table"

**Strengths.** This is the most *architecturally honest* of the five ideas. While Ideas 1–3 organize AI by workflow, history, or capability, Idea 4 organizes it by *dependency* — what literally sits on top of what. This mirrors how AI systems are actually built and debugged in production: when something breaks, you troubleshoot layer by layer from hardware up through serving. The vertical stack metaphor is immediately legible to anyone with a software engineering background because it echoes familiar mental models (OSI network layers, the frontend/backend/database stack, the TCP/IP layer cake). The "compounds at intersections" concept is the idea's most original contribution — showing how RAG isn't a single element but a compound formed from the Data Layer and Model Families is a genuinely useful way to teach people that most "products" they interact with are multi-layer assemblies, not monolithic capabilities. The "energy level" icon (compute intensity) adds a dimension none of the other ideas capture: cost. For CTOs and architects making build-vs-buy decisions, knowing that an element is compute-extreme versus compute-light is directly actionable. This is the only idea that takes infrastructure economics seriously.

**Weaknesses.** The vertical stack metaphor, while powerful, imposes a strict hierarchy that doesn't always reflect reality. In practice, the layers are not cleanly independent — choices at the Framework layer constrain Architecture options, model family selection dictates hardware requirements, and governance concerns should permeate every layer rather than sitting neatly on top. The real-table analogy also strains here: the chemistry periodic table and the SEO table are both *flat grids* where position encodes category and importance. A vertical stack is a different visual paradigm entirely — it's more of an infographic or systems diagram than a "periodic table." If the brief is specifically to create something recognizable as a periodic table, this idea drifts furthest from that form factor. The "compounds at intersections" concept, while intellectually appealing, creates a design challenge: how do you visually represent intersection products in a layered grid without the poster becoming a tangled dependency graph? There's a real risk of visual overload. Finally, infrastructure evolves at different speeds — hardware changes on 2–3 year cycles, frameworks on 6–12 month cycles, and governance on multi-year regulatory timelines. A single snapshot struggles to capture these different clock speeds without feeling immediately outdated at some layers.

**Mitigations.** Hybridize the layout: keep the vertical stack as the primary organizing axis (rows = layers) but use columns within each layer to create a grid structure that evokes the periodic table format. This gives you both the stack metaphor *and* the familiar grid aesthetic. For compounds, dedicate a separate panel (like the Niches section in the SEO table or the Lanthanide strip in chemistry) rather than trying to overlay them on the main grid. For the permeation problem (governance should touch every layer), use a vertical sidebar or color overlay — similar to how some chemistry tables shade electron orbital blocks across the entire grid. For clock-speed differences, add a "stability indicator" to each layer header: Hardware (stable, multi-year cycles), Frameworks (volatile, sub-year cycles), Governance (emerging, regulatory-dependent).

**Verdict.** This is the most practically useful idea for technical decision-makers — CTOs, platform engineers, MLOps teams, and infrastructure investors. It answers questions the other ideas don't: "What do I need to build this?" "What's the most expensive layer?" "Where are the vendor lock-in risks?" Its weakness as a "periodic table" (it's really a stack diagram) is also its strength as an *industry reference*. If you relax the requirement that it must look exactly like Mendeleev's grid, this becomes the most actionable poster you could pin above an engineering team's whiteboard. The hybrid layout described above threads the needle: periodic-table feel with stack-diagram substance.

---

## Detailed Version: The Full-Stack AI Infrastructure Periodic Table

### Structural Principles

The table is organized as a *layered grid*. Eight horizontal layer-rows stack from bottom (closest to physics) to top (closest to the end user), representing the full dependency chain of a modern AI system. Within each layer, elements are arranged in columns by functional sub-category, creating a grid that reads both vertically (dependency) and horizontally (variety within a layer). This hybrid gives the table a periodic-table silhouette while preserving the stack metaphor.

**Layers (Bottom to Top):** Each layer depends on the layers below it. You cannot have models without frameworks, frameworks without compute, or compute without hardware.

**Energy Level Icon (⚡):** Each element carries a compute/cost intensity rating from ⚡ (minimal — runs on a laptop) to ⚡⚡⚡⚡⚡ (extreme — requires dedicated cluster-scale infrastructure). This is the unique axis of this table: it makes the invisible cost dimension visible.

**Maturity Indicator:** Each element also carries a maturity tag — **Established** (industry standard, multiple vendors), **Maturing** (adopted by leaders, consolidating), **Emerging** (early adopters only, rapidly evolving), or **Experimental** (research-stage, pre-production). This helps readers distinguish between elements they can bet on today versus elements they should watch.

**Compound Products Panel:** A dedicated section below the main grid shows how elements from different layers combine to form the products and patterns people actually interact with. Each compound lists its constituent elements by layer, like a chemical formula.

**Governance Permeation Sidebar:** Rather than placing governance only at the top layer, a vertical gold sidebar runs along the right edge of the entire table, with governance elements positioned at the layer where they most directly intervene. This visually communicates that governance is not an afterthought bolted on top but a concern that touches every level of the stack.

**Element Tile Format:**
```
┌──────────────────────────┐
│ ⚡⚡⚡⚡       Maturing    │
│          Pt              │
│     PyTorch              │
│  Eager-mode deep         │
│  learning framework      │
│  FRAMEWORKS & TOOLING    │
└──────────────────────────┘
```
Top-left: energy level. Top-right: maturity tag. Center: symbol and name. Below: one-line description. Bottom: layer label. Color is determined by layer.

---

### Layer 1 — HARDWARE & SILICON (Charcoal / Dark Gray)
*The physical substrate. Everything in AI ultimately reduces to transistors moving numbers.*

**Stability: High** — Hardware changes on 18–36 month cycles. Choices here lock you in for years.

| ⚡ | Mat. | Sym | Element | Description |
|---|---|---|---|---|
| ⚡⚡⚡⚡⚡ | Established | **Gp** | GPU (NVIDIA) | The default AI workhorse. CUDA ecosystem dominance from training through inference. H100/B200 era. |
| ⚡⚡⚡⚡⚡ | Maturing | **Tp** | TPU (Google) | Tensor Processing Units purpose-built for matrix operations. Tightly coupled with JAX and GCP. |
| ⚡⚡⚡⚡ | Emerging | **Cs** | Custom AI Silicon | AWS Trainium/Inferentia, Meta MTIA, Microsoft Maia, Groq LPU. The diversification wave challenging NVIDIA's monopoly. |
| ⚡⚡⚡ | Established | **Cp** | CPU Clusters | Still relevant for inference of smaller models, classical ML workloads, and preprocessing pipelines. |
| ⚡⚡⚡ | Emerging | **Ed** | Edge AI Chips | Apple Neural Engine, Qualcomm Hexagon, MediaTek APU. On-device inference for mobile and IoT. |
| ⚡⚡ | Emerging | **Nr** | Neuromorphic Chips | Intel Loihi, IBM NorthPole. Brain-inspired architectures optimized for sparse, event-driven computation. Ultra-low power. |
| ⚡⚡⚡⚡⚡ | Experimental | **Qc** | Quantum Co-Processors | Quantum hardware for specific AI sub-problems (optimization, sampling). Not yet practical for mainstream ML. |
| ⚡⚡⚡⚡ | Established | **Nw** | Networking / Interconnects | NVLink, InfiniBand, RoCE. The data highways between GPUs in multi-node training. Often the real bottleneck. |
| ⚡⚡⚡ | Established | **Mm** | High-Bandwidth Memory | HBM3, HBM3e. Memory bandwidth is the binding constraint for LLM inference throughput. |

---

### Layer 2 — COMPUTE & ORCHESTRATION (Steel Blue)
*Turning raw hardware into usable, schedulable, parallelized computational power.*

**Stability: Medium** — Orchestration patterns evolve on 12–24 month cycles as model sizes and training paradigms shift.

| ⚡ | Mat. | Sym | Element | Description |
|---|---|---|---|---|
| ⚡⚡⚡⚡⚡ | Maturing | **Dp** | Data Parallelism | Distributing training batches across multiple devices. The simplest and most common multi-GPU strategy (DDP, FSDP). |
| ⚡⚡⚡⚡⚡ | Maturing | **Tp** | Tensor Parallelism | Splitting individual layers across devices for models too large to fit on a single GPU. Megatron-LM style. |
| ⚡⚡⚡⚡⚡ | Maturing | **Pp** | Pipeline Parallelism | Splitting model layers sequentially across devices. Enables training of very deep models with managed memory. |
| ⚡⚡⚡⚡ | Established | **Sc** | Job Scheduling | SLURM, Kubernetes, Ray — orchestrating training jobs, managing queues, handling preemption and checkpointing. |
| ⚡⚡⚡ | Maturing | **Sv** | Inference Serving | vLLM, TensorRT-LLM, Triton. Optimized serving runtimes with continuous batching, paged attention, speculative decoding. |
| ⚡⚡⚡ | Maturing | **Sp** | Speculative Decoding | Using a small draft model to propose tokens that a larger model verifies in parallel. Reduces latency without quality loss. |
| ⚡⚡⚡⚡ | Emerging | **Ex** | Expert Routing | Dynamic routing infrastructure for Mixture-of-Experts models — activating only relevant sub-networks per input. |
| ⚡⚡ | Established | **Ck** | Checkpointing & Recovery | Saving training state periodically so multi-day runs can survive hardware failures without restarting from scratch. |
| ⚡⚡⚡ | Emerging | **Ea** | Elastic Training | Dynamically scaling GPU count up or down during training based on availability and cost, without job interruption. |

---

### Layer 3 — DATA LAYER (Olive Green)
*Collection, curation, storage, and governance of the information that models learn from and retrieve.*

**Stability: Low-Medium** — Data practices are evolving rapidly under regulatory and quality pressure.

| ⚡ | Mat. | Sym | Element | Description |
|---|---|---|---|---|
| ⚡⚡⚡⚡ | Established | **Wc** | Web Crawl Corpora | Common Crawl, FineWeb, RefinedWeb. The bulk raw material for pre-training language models. |
| ⚡⚡⚡ | Maturing | **Cd** | Curated Datasets | Carefully assembled, quality-filtered collections. The Pile, RedPajama, Dolma. Quality over quantity movement. |
| ⚡⚡⚡ | Maturing | **Sd** | Synthetic Data Generation | Using models to generate training data for other models. Distillation-based, simulation-based, or augmentation-based. |
| ⚡⚡ | Established | **Lb** | Labeling & Annotation | Human annotation pipelines (Scale AI, Surge, internal teams) and increasingly AI-assisted labeling. |
| ⚡⚡⚡ | Maturing | **Dd** | Deduplication & Cleaning | MinHash, exact-match, and semantic dedup pipelines. Proven to improve model quality per training FLOP. |
| ⚡⚡ | Maturing | **Tk** | Tokenization | BPE, SentencePiece, Unigram. The bridge between raw text and model-consumable integers. Subtle but consequential. |
| ⚡⚡⚡ | Emerging | **Pv** | Data Provenance & Licensing | Tracking where data came from, under what terms, and whether it's legally usable. Spawning AI, Data Provenance Initiative. |
| ⚡⚡ | Emerging | **Dp** | Data Privacy Tooling | Differential privacy implementations, PII scrubbing, federated data access. Driven by GDPR, CCPA, and AI Act compliance. |
| ⚡⚡ | Emerging | **Vl** | Data Valuation | Techniques for quantifying the contribution of individual data points or datasets to model performance. Shapley values, influence functions. |

---

### Layer 4 — ALGORITHMS & MATHEMATICS (Deep Purple)
*The theoretical engines — loss functions, optimization methods, and architectural innovations that define how learning happens.*

**Stability: Medium** — Core algorithms are stable; innovations at the frontier arrive every few months.

| ⚡ | Mat. | Sym | Element | Description |
|---|---|---|---|---|
| ⚡⚡⚡ | Established | **At** | Attention Mechanism | Scaled dot-product attention, multi-head attention, and variants (flash, grouped-query, sliding window). The core innovation of the transformer era. |
| ⚡⚡⚡ | Established | **Gd** | Gradient Descent & Variants | Adam, AdaFactor, LAMB, Lion. The optimization algorithms that drive all neural network training. |
| ⚡⚡⚡ | Established | **Ls** | Loss Functions | Cross-entropy, MSE, contrastive, triplet, DPO preference loss. The mathematical definition of "what the model is trying to do." |
| ⚡⚡ | Established | **Rg** | Regularization | Dropout, weight decay, label smoothing, spectral normalization. Techniques that prevent overfitting and improve generalization. |
| ⚡⚡⚡⚡ | Established | **Bp** | Backpropagation & Autodiff | Automatic differentiation engines that compute gradients through arbitrary computational graphs. The unsung hero of deep learning. |
| ⚡⚡⚡ | Maturing | **Df** | Diffusion / Flow Matching | Score-based denoising and continuous normalizing flows. The mathematical framework behind image, video, and audio generation. |
| ⚡⚡⚡ | Maturing | **Ct** | Contrastive Learning | Learning representations by pulling similar items together and pushing dissimilar items apart in embedding space. CLIP, SimCLR, MoCo. |
| ⚡⚡ | Emerging | **Ss** | State-Space Formulations | Mamba, S4, and linear attention variants. Recurrence-based alternatives to attention with linear scaling in sequence length. |
| ⚡⚡⚡⚡ | Established | **Rl** | RL Algorithms | PPO, DPO, GRPO, SAC. Policy optimization methods used for game-playing, robotics, and LLM alignment via human feedback. |

---

### Layer 5 — FRAMEWORKS & TOOLING (Teal)
*The software ecosystem that practitioners actually touch daily — libraries, platforms, and developer tools.*

**Stability: Low** — The fastest-moving layer. Framework dominance can shift within a single year.

| ⚡ | Mat. | Sym | Element | Description |
|---|---|---|---|---|
| ⚡⚡⚡⚡ | Established | **Pt** | PyTorch | The dominant research and increasingly production framework. Eager execution, rich ecosystem, Meta-backed. |
| ⚡⚡⚡⚡ | Maturing | **Jx** | JAX | Google's functional transformation framework (grad, jit, vmap, pmap). Preferred for large-scale TPU training and research requiring composable transforms. |
| ⚡⚡⚡ | Established | **Hf** | HuggingFace Ecosystem | Model Hub, Transformers library, Datasets, Tokenizers, Spaces. The "GitHub of ML" — the default starting point for model distribution and experimentation. |
| ⚡⚡⚡ | Maturing | **Lc** | LangChain / LlamaIndex | Orchestration frameworks for LLM application pipelines: chaining prompts, tools, retrieval, and memory. Rapidly evolving and sometimes criticized for over-abstraction. |
| ⚡⚡⚡ | Maturing | **Vd** | Vector Databases | Pinecone, Weaviate, Qdrant, Chroma, pgvector. Specialized storage and retrieval for embedding vectors. The backbone of RAG pipelines. |
| ⚡⚡ | Maturing | **Wb** | Experiment Tracking | Weights & Biases, MLflow, Neptune. Logging hyperparameters, metrics, artifacts, and enabling reproducibility across training runs. |
| ⚡⚡ | Maturing | **Ev** | Evaluation Frameworks | HELM, LM-Eval-Harness, Inspect. Standardized tooling for running benchmarks and comparing models consistently. |
| ⚡⚡⚡ | Emerging | **Ag** | Agent Frameworks | Claude Code, OpenAI Codex CLI, AutoGen, CrewAI. Tooling for building multi-step autonomous AI agent systems. The most volatile sub-category on the entire table. |
| ⚡⚡ | Emerging | **Gt** | Guardrail Libraries | NeMo Guardrails, Guardrails AI, Anthropic's constitutional approach. Tooling for constraining model outputs to safe, structured, policy-compliant formats. |

---

### Layer 6 — MODEL FAMILIES (Crimson)
*The trained models themselves — the learned artifacts that embody intelligence.*

**Stability: Low** — New model families and capability jumps arrive quarterly. The most visible and hyped layer.

| ⚡ | Mat. | Sym | Element | Description |
|---|---|---|---|---|
| ⚡⚡⚡⚡⚡ | Established | **Lm** | Large Language Models | GPT-4, Claude, Gemini, Llama, Mistral. Autoregressive transformers trained on text at scale. The defining model family of the current era. |
| ⚡⚡⚡⚡⚡ | Maturing | **Dm** | Diffusion Image Models | Stable Diffusion, DALL-E, Midjourney, Imagen. Text-to-image generation via iterative denoising. |
| ⚡⚡⚡⚡⚡ | Emerging | **Vm** | Video Generation Models | Sora, Runway, Kling, Veo. Text/image-to-video via diffusion or autoregressive methods. Compute-extreme and quality-inconsistent. |
| ⚡⚡⚡⚡ | Maturing | **Mm** | Multimodal Models | GPT-4o, Claude (vision), Gemini. Models that natively process and generate across text, image, audio, and code. |
| ⚡⚡⚡⚡ | Maturing | **Em** | Embedding Models | E5, BGE, Voyage, Cohere Embed. Models that map inputs to dense vector representations for search and retrieval. |
| ⚡⚡⚡⚡ | Emerging | **Rm** | Reasoning Models | o1/o3, Claude extended thinking, Gemini thinking. Models with explicit multi-step deliberation at inference time. |
| ⚡⚡⚡ | Maturing | **Sm** | Small Language Models | Phi, Gemma, Llama-3-8B, Mistral-7B. Capable models optimized for efficiency, edge deployment, and fine-tuning accessibility. |
| ⚡⚡⚡⚡ | Emerging | **Am** | Audio / Speech Models | Whisper, Bark, ElevenLabs, MusicGen. Speech recognition, synthesis, and music generation models. |
| ⚡⚡⚡ | Emerging | **Cd** | Code-Specialized Models | Codex, StarCoder, DeepSeek-Coder, CodeLlama. Models specifically trained or fine-tuned for software engineering tasks. |
| ⚡⚡⚡⚡ | Experimental | **Wm** | World Models | Video prediction, physics simulation, environment modeling. Models that learn implicit or explicit representations of how the world works. |

---

### Layer 7 — INTERFACES & DELIVERY (Sky Blue)
*How AI reaches end users — the APIs, UIs, protocols, and interaction paradigms that make models usable.*

**Stability: Low-Medium** — Interface patterns are consolidating around a few dominant paradigms, but new modalities keep emerging.

| ⚡ | Mat. | Sym | Element | Description |
|---|---|---|---|---|
| ⚡⚡ | Established | **Ap** | REST / Streaming APIs | The primary programmatic interface. JSON in, tokens out, with streaming for real-time delivery. OpenAI-compatible format becoming a de facto standard. |
| ⚡⚡ | Maturing | **Ch** | Chat Interfaces | Claude.ai, ChatGPT, Gemini. Conversational web/mobile UIs that are the primary consumer touchpoint for LLMs. |
| ⚡⚡ | Maturing | **Cp** | Copilot / IDE Integration | GitHub Copilot, Cursor, Claude Code. AI embedded directly into developer workflows with context-aware assistance. |
| ⚡⚡ | Emerging | **Mc** | MCP (Model Context Protocol) | Open protocol for connecting models to external tools and data sources. Standardizing how models interact with the world. |
| ⚡⚡ | Emerging | **Pg** | Plugin / Extension Ecosystems | GPT Actions, Claude MCP servers, Gemini extensions. Marketplaces for third-party tool integrations. |
| ⚡⚡ | Emerging | **Vc** | Voice Interfaces | Real-time voice-to-voice AI conversation. Advanced Voice Mode, Gemini Live. Moving beyond text as the default modality. |
| ⚡⚡ | Emerging | **Ca** | Canvas / Artifact Interfaces | Persistent workspaces (Claude Artifacts, ChatGPT Canvas) where AI and human co-edit documents, code, and designs side by side. |
| ⚡ | Emerging | **Sd** | SDK & Client Libraries | Official language-specific client libraries (Python, TypeScript, Go) that abstract API complexity and add type safety. |
| ⚡⚡ | Experimental | **Eb** | Embodied Interfaces | Robotics control, AR/VR integration, physical-world actuation. AI controlling things you can touch. |

---

### Layer 8 — GOVERNANCE & TRUST (Gold)
*The policies, practices, standards, and legal frameworks that determine whether AI is deployed responsibly.*

**Stability: Very Low** — The most rapidly evolving layer due to regulatory activity worldwide. Also the most geographically fragmented.

| ⚡ | Mat. | Sym | Element | Description |
|---|---|---|---|---|
| ⚡ | Emerging | **Rg** | Regulation (AI Act, EO) | EU AI Act, US Executive Orders, China's AI regulations. Legally binding requirements on risk classification, transparency, and compliance. |
| ⚡ | Maturing | **Mc** | Model Cards & Documentation | Standardized disclosure of model capabilities, limitations, training data, and intended use. Mitchell et al. framework. |
| ⚡⚡ | Maturing | **Rt** | Red-Teaming Programs | Organized adversarial testing by internal teams, external contractors, or bug-bounty-style programs. Becoming an industry norm. |
| ⚡⚡ | Emerging | **Al** | Alignment Research | Constitutional AI, RLHF, interpretability, formal verification. The scientific effort to make models reliably follow human intent. |
| ⚡ | Emerging | **Au** | Audit & Compliance | Third-party auditing of AI systems for bias, safety, and regulatory compliance. Nascent industry with few standards. |
| ⚡ | Emerging | **Ip** | IP & Copyright Frameworks | Legal frameworks governing training data rights, output ownership, and creator compensation. NYT v. OpenAI era. |
| ⚡ | Emerging | **Wk** | AI Watermarking | Embedding detectable signatures in AI-generated content (text, image, audio) for provenance and authenticity tracking. C2PA, SynthID. |
| ⚡⚡ | Emerging | **Sf** | Safety Benchmarks | Standardized evaluations for harmful outputs, jailbreak resistance, and alignment properties. MLCommons AI Safety, NIST AISIC. |
| ⚡ | Experimental | **Li** | Liability Frameworks | Legal doctrines for assigning responsibility when AI systems cause harm. Product liability vs. negligence vs. strict liability. Almost entirely unresolved. |

---

### COMPOUND PRODUCTS PANEL

This section shows how elements from multiple layers combine to form recognizable products and patterns. Each compound lists its formula as a layer-by-layer assembly.

| Compound | What It Is | Formula (Layer → Element) |
|---|---|---|
| **RAG Pipeline** | Retrieval-augmented generation system | Data(Cd + Tk) + Algorithms(At + Ct) + Frameworks(Vd + Lc) + Models(Lm + Em) + Interfaces(Ap) |
| **AI Code Assistant** | IDE-integrated coding copilot | Hardware(Gp) + Compute(Sv + Sp) + Data(Cd) + Models(Cd + Lm) + Interfaces(Cp) + Governance(Mc) |
| **Text-to-Video Pipeline** | End-to-end video generation system | Hardware(Gp × many) + Compute(Tp + Pp) + Data(Wc + Sd) + Algorithms(Df) + Frameworks(Pt) + Models(Vm) + Interfaces(Ap + Ch) |
| **Enterprise AI Chatbot** | Customer-facing conversational agent with guardrails | Data(Cd + Pv) + Frameworks(Vd + Gt + Lc) + Models(Lm + Em) + Interfaces(Ch + Ap) + Governance(Mc + Rt + Rg) |
| **Autonomous AI Agent** | Multi-step task-completing agent with tool use | Compute(Sv) + Frameworks(Ag + Vd) + Models(Rm + Lm) + Interfaces(Mc + Ap) + Governance(Al + Sf + Rt) |
| **On-Device Voice Assistant** | Phone/watch-based AI with local inference | Hardware(Ed + Mm) + Compute(Sv) + Models(Sm + Am) + Interfaces(Vc + Sd) |
| **AI Safety Evaluation Suite** | Comprehensive model safety testing pipeline | Data(Cd + Lb) + Frameworks(Ev + Gt) + Models(Lm) + Governance(Rt + Sf + Au) |
| **Federated Healthcare Model** | Privacy-preserving model trained across hospitals | Hardware(Cp) + Data(Dp + Pv + Lb) + Algorithms(Gd + Rg) + Frameworks(Pt + Wb) + Governance(Rg + Au + Li) |

---

### GOVERNANCE PERMEATION SIDEBAR

Running vertically along the right edge of the entire table, this gold-colored sidebar maps governance concerns to the specific layer where they most directly intervene. This visually communicates that governance is not just "Layer 8" — it threads through the entire stack.

| Layer Touched | Governance Concern | Description |
|---|---|---|
| **Hardware** | Export Controls | US CHIPS Act restrictions, entity lists limiting GPU sales to certain countries. Governance at the physics layer. |
| **Compute** | Compute Reporting Thresholds | Proposed requirements to report training runs above certain FLOP thresholds. AI Act and US EO provisions. |
| **Data** | Consent & Copyright | Whether training data was collected with appropriate rights. The foundational legal question of the AI era. |
| **Data** | Privacy Regulation | GDPR, CCPA, and sector-specific rules (HIPAA) governing what data can be used and how. |
| **Algorithms** | Algorithmic Bias Standards | NIST AI RMF, IEEE standards for fairness testing at the algorithmic level before deployment. |
| **Frameworks** | Supply Chain Security | Dependency auditing, model provenance verification, protection against poisoned packages or compromised model weights. |
| **Models** | Safety Evaluation Mandates | Requirements to evaluate models for dangerous capabilities (bio, cyber, CBRN) before release. Frontier model policies. |
| **Interfaces** | Transparency & Disclosure | Requirements to inform users they're interacting with AI. Watermarking mandates for generated content. |
| **All Layers** | Liability & Insurance | The cross-cutting question: when something goes wrong, which layer is responsible, and who pays? |

---

### Reading the Table — Interpretive Keys

**Vertical Reading (Top to Bottom within a column)** answers "What's the full dependency chain for this capability?" Trace a line from an Interface element down through every layer it depends on. A Chat Interface depends on a Serving runtime, which depends on a Model, which depends on Training Algorithms, which depend on a Framework, which depends on Compute Orchestration, which depends on Hardware. Every production outage is a story about one link in this chain breaking.

**Horizontal Reading (Left to Right within a layer)** answers "What are my options at this level?" Within the Compute layer, you choose between data parallelism, tensor parallelism, and pipeline parallelism. Within Frameworks, you choose between PyTorch and JAX. The table makes these option spaces visible and comparable.

**Energy Level Scanning (⚡ icons)** provides an instant cost topology. Scanning the ⚡ column reveals that the middle layers (Compute, Data, Models) are where the money goes, while Interfaces and Governance are relatively cheap in compute but expensive in human effort. This insight alone makes the table valuable for budgeting.

**The Compound Panel** is the table's key pedagogical contribution. It teaches readers that "ChatGPT" is not a single thing — it's a compound assembled from ~6 layers of distinct elements. This decomposition skill is exactly what non-technical stakeholders lack and desperately need. When a CEO asks "Why can't we just build our own ChatGPT?", the compound formula is the answer: here are the 15 elements you'd need, across 7 layers, at these energy levels.

**Layer Stability Indicators** appear in the layer header row. A slow-spinning gear icon (⚙) for stable layers (Hardware, Algorithms), a fast-spinning icon (⚡⚙) for volatile layers (Frameworks, Models, Governance). This helps readers calibrate how much their decisions at each layer will need to be revisited.

---

### Visual & Design Notes

The poster uses a portrait 24"×36" format, oriented vertically to emphasize the stack metaphor. Layers progress from bottom to top, with the heaviest/most physical layer (Hardware) at the base and the most abstract layer (Governance) at the top — just as geological strata place bedrock at the bottom and atmosphere at the top. Each layer gets a distinct color band: dark grays at the bottom transitioning through blues, greens, and purples in the middle to gold at the top. The Compound Products Panel sits in a separate landscape-oriented band across the bottom of the poster, below the Hardware layer, styled as a "workbench" where elements are assembled. The Governance Permeation Sidebar runs as a thin gold ribbon along the right edge with small callout arrows pointing into each layer.

A companion interactive web version allows users to click any Compound Product and see its constituent elements light up across the stack — a visual "X-ray" that makes the dependency chain tangible. Users can also create custom compounds by selecting elements from each layer, generating a shareable "architecture card" for their own AI system. This interactive mode transforms the static poster into a planning tool, bridging the gap between educational reference and practical utility.
