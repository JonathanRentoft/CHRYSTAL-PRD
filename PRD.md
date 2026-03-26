# CRYSTAL — Crystal Reasoning AI
## Master PRD v4.3 — Five Properties Edition
### CRYSTAL.ai | Complete, Definitive, No Holes

> *"The first machine that generates understanding rather than retrieves it."*

**Version:** 4.3 — Five Properties Edition  
**Build Target:** 28 days to first public demo  
**Hardware:** Mac M1 32GB → Hetzner A100  
**Paradigm:** Thinking, not Remembering  
**Goal:** Beat every AI on every dimension. ~3.5GB. No fallbacks. No exceptions.

> ⚠️ **v4.1.1:** This build includes the **Multi-Brain Isolation** fix —
> all crystal, bond, and axiom data is scoped to `data/brains/{ACTIVE_BRAIN}/`,
> enabling safe branching, testing, and rollback without corrupting production data.

> ⚠️ **v4.2 Update:** The PRD has been updated inline with the Living Intelligence Architecture (Module 10, Core Ontology, Edge/Cloud modes).

> ⚠️ **v4.3 Update:** Five Properties of Understanding (Section 1.3), Dream Engine (Module 11), Compression Engine (Module 12), MCTS reasoning, self-improvement training loop, updated deployment modes, and implementation roadmap (Section 8).

---

## TABLE OF CONTENTS

1. [Philosophy — Why Every AI Built Today Is Wrong](#1-philosophy)
2. [Architecture — The Seven Cognitive Modules](#2-architecture)
3. [Module Specifications — Complete Technical Detail](#3-modules)
   - 3.8 [Module 0 — Query Parser](#38-module-0--query-parser) *(v4.1)*
   - 3.8.5 [Module 8 — Audit Logger](#385-module-8--audit-logger-eu-ai-act-article-12) *(v4.1)*
   - 3.9 [Error Handling & Retry Policy](#39-error-handling--retry-policy) *(v4.1)*
   - 3.10 [Module 9 — Public Interface](#310-module-9--public-interface) *(v4.1)*
   - 3.11 [Module 10 — Active Learning Engine](#311-module-10--active-learning-engine) *(v4.2)*
4. [The Gemini Deep Research Fixes — Five Fatal Bypasses](#4-gemini-fixes)
5. [Axiom Layer — First Principles Derivation](#5-axioms)
6. [Complete Query Routing Flow](#6-routing)
7. [Safety Architecture](#7-safety)
   - 7.5 [Article 12 Compliance — Encrypted Append-Only Audit Log](#75-article-12-compliance--encrypted-append-only-audit-log)
8. [The Five Properties Implementation Roadmap](#8-the-five-properties-implementation-roadmap) *(v4.3)*
   - 8.1 [Property 1 — Generative (Axiom Composition)](#81-property-1--generative-axiom-composition)
   - 8.2 [Property 2 — Compact (Compression Engine)](#82-property-2--compact-compression-engine)
   - 8.3 [Property 3 — Compositional (DSL Library Learning)](#83-property-3--compositional-dsl-library-learning)
   - 8.4 [Property 4 — Causally Correct (Interventional Verification)](#84-property-4--causally-correct-interventional-verification)
   - 8.5 [Module 11 — Dream Engine](#85-module-11--dream-engine)
   - 8.6 [Two Deployment Modes (Expanded)](#86-two-deployment-modes-expanded)
   - 8.7 [Inference-Time Compute Scaling (MCTS)](#87-inference-time-compute-scaling-mcts-over-reasoning-programs)
   - 8.8 [Self-Improvement Training Loop](#88-self-improvement-training-loop)
   - 8.9 [Analogy Engine](#89-analogy-engine--cross-domain-structural-reasoning) *(v4.3)*
   - 8.10 [Emergent Abstraction Hierarchy](#810-emergent-abstraction-hierarchy) *(v4.3)*
   - 8.11 [Evolving Domain-Specific Reasoning Languages](#811-evolving-domain-specific-reasoning-languages) *(v4.3)*
   - 8.12 [Knowing What Cannot Be Known](#812-knowing-what-cannot-be-known) *(v4.3)*
9. [Ten-Year Edge Case Register](#9-ten-year-edge-case-register)
10. [Environment Setup](#10-setup)
    - 10.1 [Logging & Observability](#101-logging--observability) *(v4.1)*
11. [28-Day Build Plan — Day by Day](#11-28-day-build-plan--day-by-day)
12. [Performance Targets](#12-performance)
13. [All Datasets — All Free](#13-datasets)
14. [The arXiv Paper](#14-paper)
15. [The Launch](#15-launch)
16. [Definition of Done](#16-done)
17. [Vision — What This Becomes](#17-vision)

---

## 1. PHILOSOPHY

### 1.1 Why Everything Else Is Wrong

Every artificial intelligence system ever built shares one foundational assumption that is architecturally incorrect: **intelligence is fundamentally about storage and retrieval.**

GPT-4, Gemini, Claude, Grok — regardless of size, capability, or benchmark score — are extraordinarily sophisticated filing cabinets. They compress the statistical residue of human text into weight matrices and retrieve plausible continuations. This is not thinking. It has never been thinking. It is a very impressive simulation of thinking built on top of a very large pattern-matching engine.

> A four-year-old child who has never been told how a see-saw works understands it completely within minutes of encountering one. No stored fact. No training data. No retrieval. They build a causal model and simulate it. They can predict what happens when the weight shifts. They can explain why. They can design experiments.
>
> That is thinking. Not retrieval. Not prediction. **Causal simulation.**
>
> CRYSTAL is the first AI architecture built around this principle.

### 1.2 The Five Diseases of Current AI

| Disease | Symptom | CRYSTAL's Solution |
|---------|---------|-------------------|
| Statistical mimicry | Hallucination — plausible text with no grounding | Causal simulation over verified crystal library |
| Monolithic weights | One wrong parameter corrupts everything | Modular crystal library — surgical editability |
| Black-box reasoning | Cannot explain or verify its own answers | Full simulation trace on every answer |
| Centralised training | No genuine personalisation, no privacy | On-device personal crystal layer, no cloud |
| No epistemic honesty | Confidently wrong — cannot say "I don't know" | Epistemic Monitor computes confidence mechanically |

### 1.3 The Five Properties of Understanding

A system that genuinely understands a phenomenon F possesses a model M with five 
measurable properties:

**Property 1 — Generative:** M produces predictions for interventions and contexts 
never observed. Not interpolation between known points. Extrapolation to new regions 
of input space. "What happens if I heat ice in a vacuum?" — answerable without ever 
having observed it, by composing axioms.

**Property 2 — Compact (MDL):** M's description length is dramatically shorter than 
enumerating all predictions it can produce. |M| << |{all predictable outcomes}|. 
Newton's laws are a few lines. They predict infinite motions. A lookup table of the 
same motions is not understanding.

**Property 3 — Compositional:** M is built from parts that recombine. The child's 
seesaw model uses "gravity," "balance," "distance." The SAME parts model doors, 
hammers, bridges. Understanding one domain transfers to others because they share 
components.

**Property 4 — Causally correct:** M's structure mirrors the phenomenon's ACTUAL 
causal structure. Not correlations. The child understands that weight CAUSES the side 
to go down. Proof: they can predict interventions — "what happens IF I place a stone?" 
Correct interventional prediction requires causal models.

**Property 5 — Locally updatable:** When M's prediction is wrong, the specific 
component that failed can be adjusted without destroying the rest. A child who discovers 
wind affects seesaws adds "wind" to the model. They don't rebuild their entire 
understanding from scratch.

**CRYSTAL implements all five as engineering approximations:**

| Property | Mechanism | Module | Status |
|----------|-----------|--------|--------|
| Generative | Axiom composition — derive answers for unseen combinations | DerivationEngine | Architecture complete, axioms pending |
| Compact (MDL) | Compression loop — find minimal axiom set that generates bond store | CompressionEngine | v1.0 target |
| Compositional | Library learning — discover reusable reasoning patterns from DSL execution | DSL Library Learning | v1.0 target |
| Causally correct | Interventional verification via do-calculus | CausalModel + INTERVENE | Built, needs real data |
| Locally updatable | Modular crystal/bond store — surgical edits | CrystalStore | Built and verified |

### 1.4 Two Deployment Modes (v4.2)

CRYSTAL ships in two forms:

**Cloud Intelligence (maximum reasoning)**
- Runs on server infrastructure (Hetzner A100 or equivalent)
- No size constraints — full crystal library, full bond graph, full axiom store
- Always online — can search the web, access APIs, use MCP servers
- Continuously learning — reads new material, discovers new connections, corrects errors
- Supports unlimited conversation length with persistent working memory across sessions
- This is the PRIMARY product — the intelligence people talk to

**Edge Intelligence (compressed, portable)**  
- Runs on phone/laptop — M1, iPhone, Android
- Compressed crystal library (top N most-connected crystals + their bonds)
- Fully offline capable — airplane mode reasoning with full traces
- Syncs new knowledge from cloud when online
- Target: < 1GB for core reasoning, < 3.5GB with full library
- This is the SECONDARY product — personal, private, always-available

### 1.5 Intelligence-Per-Byte Principle (v4.2)

Every architectural decision optimizes for reasoning power per byte of storage:

- Prefer 5,000 crystals with 40,000 bonds over 50,000 crystals with 40,000 bonds
  (same bond count, 10x denser graph, faster traversal, better reasoning)
- Prefer verified axioms over factual crystals 
  (one axiom "heat causes state change" replaces thousands of specific examples)
- Prefer bonds from multiple sources over single-source bonds
  (cross-referenced bonds have higher confidence, better calibration)
- Compress aggressively: packed binary HDC (256 bytes/crystal), 
  not float32 (8KB/crystal)

---

## 2. ARCHITECTURE

### 2.1 The Seven Cognitive Modules

| # | Module | Biological Analogue | Function |
|---|--------|---------------------|----------|
| 1 | Crystal Library | Long-term memory (hippocampus) | Addresses, stores, retrieves knowledge as 2,048-bit HDC binary vectors |
| 2 | Causal Graph Engine | Association cortex | Typed, directional causal relationships sourced from formal ontologies |
| 3 | Working Memory | Prefrontal cortex | Volatile session-scoped crystal store, zero degradation, arbitrary depth |
| 4 | Simulation Engine | Predictive processing cortex | Forward, backward, and counterfactual causal program execution |
| 5 | Generative Composer | Broca's area + creative cortex | Structure Encoder (60M T5-small) + Qwen2.5-Coder synthesizer + Phi-3.8B expression |
| 6 | Pragmatic Reasoner | Temporoparietal junction (TPJ) | Theory of Mind — speaker intent + cultural script → intended meaning |
| 7 | Epistemic Monitor | Anterior cingulate cortex | Mechanical confidence computation — cannot be spoofed or disabled |
| 8 | Audit Logger | N/A | EU AI Act Article 12 compliance — append-only hash-chained event log |
| 9 | Public Interface | N/A | Single entry point: CRYSTAL.ask() + CLI |
| 10 | Active Learning Engine | Curiosity/exploration drive | Web search, MCP integration, self-improvement loop |
| 11 | Dream Engine | Sleep/consolidation | Random walk discovery, bond consolidation, intelligent pruning |
| 12 | Compression Engine | Abstraction/generalization | MDL optimization — replace bonds with axioms, measure understanding depth |
| 13 | Analogy Engine | Lateral thinking / creativity | Cross-domain structural isomorphism via HDC algebra |
| 14 | Abstraction Hierarchy | Conceptual generalization | Emergent layers via recursive MDL compression |
| 15 | Undecidability Detector | Metacognitive limits | Proves when and why questions cannot be answered |
| 16 | Contradiction Miner | Cognitive dissonance | Actively hunts conflicting bonds as fuel for deeper principles |
| 17 | Curiosity Engine | Intrinsic motivation / exploration | Generates maximally informative questions via Expected Information Gain |
| 18 | Adversarial Self-Debate | Critical self-reflection | Internal devil's advocate — attacks own answers before returning them |
| 19 | Perspective Simulator | Theory of Mind / empathy | Runs same query through multiple domain-DSLs, synthesizes across viewpoints |
| 20 | Temporal Simulator | Episodic memory / future planning | Propagates state changes through causal bonds over time |

### 2.2 The Architecture Invariants

```
INVARIANT 1: Modules communicate only through defined interfaces.
             No cross-layer direct access.

INVARIANT 2: The crystal library is the single source of truth for world knowledge.

INVARIANT 3: The simulation engine is the single point of answer generation.

INVARIANT 4: The epistemic monitor has read access to all modules.
             It cannot be bypassed. Ever.

INVARIANT 5: Phi-3.8B has NO access to the crystal library.
             It receives structured JSON only. It cannot reason or retrieve.
             It is the mouth. The crystal system is the brain.

INVARIANT 6: The Dream Engine runs ONLY when the system is idle.
             It cannot interrupt active query processing.
             All discoveries are CANDIDATES until verified.

INVARIANT 7: The Compression Engine never deletes a bond without
             first proving it is derivable from existing axioms.
             Compression is lossless reasoning — not data loss.

INVARIANT 8: Intelligence is measured by compression ratio:
             understanding_depth = bonds_derivable_from_axioms / total_bonds
             Target: > 0.5 means the system "understands" more than it "memorizes"

INVARIANT 9:  Analogy is structure-preserving. The Analogy Engine maps
              CAUSAL STRUCTURE, not surface similarity.
              "atom is like solar system" because of orbital structure,
              not because both are round.

INVARIANT 10: Abstraction layers emerge from compression, never from
              manual categorization. If a human has to define a category,
              the Compression Engine has failed.

INVARIANT 11: Undecidability proofs are POSITIVE results, not failures.
              The system's confidence in an undecidability proof can be
              1.0 — it is maximally confident that the question has no answer.

INVARIANT 12: Contradictions are FUEL, not errors. The Contradiction Miner
              treats every conflicting bond pair as a discovery opportunity.
              Resolution produces deeper principles than either original fact.

INVARIANT 13: The Curiosity Engine is never idle. When no user query is active,
              it generates and investigates its own questions — the ones that
              would teach the system the most.

INVARIANT 14: No answer leaves the system without surviving at least one round
              of adversarial self-attack. Answers that cannot withstand their
              own counter-arguments are downgraded, never suppressed.

INVARIANT 15: Negative knowledge (explicit NOT-bonds) has EQUAL status to
              positive knowledge. Knowing what is false is as valuable as
              knowing what is true.

INVARIANT 16: CRYSTAL's goal is not to be right. It is to be HONESTLY UNCERTAIN
              when uncertain, PROVABLY WRONG when wrong, and DEMONSTRABLY RIGHT
              when right. An answer of "I don't know, and here is exactly why"
              at confidence 0.00 is a PERFECT response — not a failure.
```

---

## 3. MODULE SPECIFICATIONS

### 3.1 Module 1 — Crystal Library (HDC Encoded)

#### 3.1.1 Why HDC, Not Embeddings

Standard embeddings are points in a learned geometric space whose meaning depends on proximity to other points — approximate, context-dependent, and unstable across retraining. HDC binary vectors are:

- **Discrete and addressed** — each crystal has a unique ID
- **Algebraically exact** — composition is reversible with zero information loss
- **Hardware-native** — all operations reduce to CPU bitwise instructions (popcount, XOR)
- **Quasi-orthogonal** — any two random 2,048-bit vectors have Hamming distance ≈ 0.5

#### 3.1.2 The Four HDC Operations

```python
def bind(a: Tensor, b: Tensor) -> Tensor:
    """Creates relationship. Reversible. Dissimilar to both inputs."""
    return a ^ b   # XOR — one CPU instruction

def bundle(vectors: list[Tensor]) -> Tensor:
    """Creates concept similar to all inputs. Encodes categories."""
    stacked = torch.stack(vectors).float()
    return (stacked.mean(dim=0) > 0.5).bool()   # majority vote

def similarity(a: Tensor, b: Tensor) -> float:
    """1.0=identical, 0.5=unrelated, 0.0=opposite."""
    return 1.0 - (a ^ b).float().mean().item()

def unbind(bound: Tensor, b: Tensor) -> Tensor:
    """Perfect algebraic inversion. Recover A from BIND(A,B) given B."""
    return bound ^ b   # XOR is its own inverse
```

#### 3.1.3 Vector Search — The Scalability Architecture

> ⚠️ **GEMINI FINDING (CRITICAL):** FAISS IndexBinaryFlat uses exhaustive brute-force search. Performance degrades exponentially beyond 100,000 vectors, violating the sub-5ms latency target at production scale.

**Solution: Adaptive search strategy by namespace**

| Index Type | Used For | Threshold | Latency |
|-----------|---------|-----------|---------|
| `FAISS IndexBinaryFlat` | Working Memory (< 500 vectors) | < 10k | Exact, nanoseconds |
| `FAISS IndexBinaryIVF` | World Crystal Library (< 10M) | 10k–50M | ~1ms, 99% recall |
| `USearch / HNSW` | Future: billion-scale | > 50M | O(log N), 92% recall |

#### 3.1.4 Crystal Data Structure

```python
@dataclass
class Crystal:
    id:           str          # globally unique, e.g. 'PARIS_001'
    concept:      str          # human-readable label
    hdc_vector:   Tensor       # 2,048-bit binary
    float_vector: Tensor       # original SAE activation, for compatibility
    layer:        int          # which model layer it was mined from
    source_model: str          # 'gemma-scope-2-9b' (M1) | 'gemma-scope-2-27b' (Hetzner) | 'eleutherai-llama3'
    source_data:  str          # 'gemma_scope' | 'wikidata_dump' | 'conceptnet'
    sae_feature_id: int        # feature index in the SAE dictionary
    confidence:   float        # extraction quality score
    domain:       list[str]    # ['geography', 'politics']
    bonds:        dict         # bond_type -> list[crystal_id]
    timestamp:    str          # ISO 8601
    personal:     bool         # False=world, True=personal
    version:      str          # library semver
```

#### 3.1.4 Crystal Data Structure

| Field | Type | Description |
|-------|------|-------------|
| `id` | `str` | Globally unique ID (e.g. 'PARIS_001') |
| `concept` | `str` | Human-readable label |
| `hdc_vector` | `Tensor` | 2,048-bit binary |
| `float_vector` | `Tensor` | Original SAE activation |
| `layer` | `int` | Source model layer |
| `source_model` | `str` | Extraction model |
| `source_data` | `str` | Raw dataset |
| `sae_feature_id` | `int` | SAE dictionary index |
| `confidence` | `float` | Quality score |
| `domain` | `list[str]` | Categories |
| `bonds` | `dict` | `bond_type` -> `list[crystal_id]` |
| `timestamp` | `str` | ISO 8601 |
| `personal` | `bool` | True if encrypted explicitly device-local |
| `version` | `str` | Version identifier |

#### 3.1.5 Crystal Store Implementation

**4 namespaces:**
- `world` — General knowledge graph
- `personal` — Encrypted, device-local
- `axioms` — Verified formal principles
- `working` — Volatile session-scoped

**Core API:**
- `add(crystal)` — Inserts to appropriate namespace index
- `search(query_hdc, top_k, namespace)` — Vector search routing to FAISS or exact matching
- `save()` — Persists non-volatile namespaces to disk
- `load()` — Restores states from storage

#### 3.1.6 Multi-Brain Versioning Architecture

Each brain is a self-contained snapshot of the entire knowledge base:

```
data/brains/
├── BRAIN_1/                        # First stable extraction
│   ├── crystal_library.json
│   ├── crystal_vectors.npy
│   ├── crystal_floats.npy
│   ├── bond_store.json
│   ├── bond_vectors.npy
│   └── axiom_store.json
├── BRAIN_2/                        # Experimental branch
│   └── ...                         # Same file set, independent data
└── BRAIN_3_wikidata_full/          # After full Wikidata seeding
    └── ...
```

**Key properties:**
- `ACTIVE_BRAIN` in `config.py` selects which brain is live (default: `'BRAIN_1'`)
- `DATA_DIR` is computed as `data/brains/{ACTIVE_BRAIN}/`
- Switching brains = changing one string. No file moves, no migrations
- Safe to branch: `cp -r data/brains/BRAIN_1 data/brains/BRAIN_2` before experiments
- Rollback: set `ACTIVE_BRAIN = 'BRAIN_1'` to revert
- `CrystalStore.save()` / `.load()` always operate on `DATA_DIR`
- Models (`data/models/`) and dumps (`data/dumps/`) are shared — not brain-scoped

#### 3.1.7 Core Ontology Principle (v4.2)

**The old approach (v4.0-v4.1):** Download everything. Dump all of Wikidata. 
Seed millions of bonds. Hope intelligence emerges from volume.

**The new approach (v4.2):** Curate a tight core ontology. 
Intelligence comes from CONNECTION DENSITY, not from raw volume.

The core ontology is structured in layers:
1. **Foundation layer** (~500 crystals): Countries, continents, elements, 
   fundamental forces, base categories (animal, plant, object, event, person)
2. **Relation layer** (~2,000 crystals): Capitals, major cities, oceans, 
   scientific concepts, historical periods, core vocabulary  
3. **Knowledge layer** (~5,000-10,000 crystals): Domain-specific concepts 
   that connect to the foundation — species, inventions, historical figures, 
   cultural concepts
4. **Living layer** (grows continuously): New crystals from web search, 
   conversations, and self-improvement

Each layer must be FULLY CONNECTED to the layer below it before adding more.
A crystal with zero bonds to the foundation is dead weight.

Quality metric: bonds-per-crystal ratio. Target > 8 for foundation, > 5 for relation, > 3 for knowledge.

#### 3.1.8 Embedding Strategy Update (v4.2)

**v4.0-v4.1 spec:** Gemma Scope SAE features only.
**v4.2 reality:** Layered approach.

- **Current (v0.2):** sentence-transformers (all-MiniLM-L6-v2) for rapid prototyping. 
  384-dim float → 2048-bit HDC. Semantic quality verified: similar concepts > 0.65, 
  dissimilar < 0.61.
- **Next (v0.3):** Gemma Scope 2 SAE features for the foundation + relation layers. 
  These capture what the model LEARNED, not just word similarity. 
  MiniLM stays as fallback for concepts SAE can't extract.
- **Future (v1.0):** Hybrid — SAE features for core concepts, MiniLM for long-tail, 
  web-search embeddings for live knowledge. All binarized to same D_CRYSTAL=2048.

---

### 3.2 Module 2 — Causal Graph Engine

> ⚠️ **GEMINI FINDING (CRITICAL):** The Wikidata SPARQL endpoint (query.wikidata.org) is in active crisis. The Blazegraph backend is unstable under 16.6 billion triples. The Wikimedia Foundation executed a "Graph Split" in 2025/2026, separating scholarly data to a separate endpoint. Live queries trigger HTTP 429 errors and 60-second timeouts.
>
> **SOLUTION:** Use offline Wikidata JSON/RDF dumps. See Section 4.3.

#### 3.2.1 Bond Type Taxonomy — v1 Production

| Bond Type | Direction | Example | Source |
|-----------|-----------|---------|--------|
| `instance-of` | specific → general | PARIS instance-of CITY | Wikidata P31 |
| `capital-of` | city → country | BERLIN capital-of GERMANY | Wikidata P36 |
| `located-in` | thing → container | PARIS located-in FRANCE | Wikidata P131 |
| `caused-by` | effect → cause | RAIN caused-by CLOUD | ConceptNet Causes |
| `part-of` | component → whole | ENGINE part-of CAR | ConceptNet PartOf |
| `opposite-of` | concept → antonym | HOT opposite-of COLD | WordNet antonyms |
| `used-for` | tool → purpose | HAMMER used-for NAILING | ConceptNet UsedFor |
| `created-by` | work → creator | GUERNICA created-by PICASSO | Wikidata P170 |
| `precedes` | event A → event B | CAUSE precedes EFFECT | ATOMIC xEffect |
| `property-of` | attribute → entity | BLUE property-of SKY | ConceptNet HasProperty |
| `has-prerequisite` | effect → precondition | FLYING has-prereq AIRCRAFT | ConceptNet HasPrereq |
| `desires` | agent → goal | HUMAN desires FOOD | ATOMIC xWant |

#### 3.2.2 Causal Edge Structure

```python
@dataclass
class CausalEdge:
    source_id:    str      # cause crystal ID
    target_id:    str      # effect crystal ID
    bond_type:    str      # from taxonomy above
    hdc_encoded:  Tensor   # BIND(source_hdc, BIND(role_vec, target_hdc))
    confidence:   float    # from source weight or manual review
    provenance:   str      # 'wikidata_dump' | 'conceptnet' | 'atomic2020' | 'synthetic'
    verified:     bool     # True if cross-referenced by 2+ sources
    domain:       str      # primary domain
```

#### 3.2.3 Reasoning Shortcuts — The Threat and The Fix

> ⚠️ **GEMINI FINDING:** Neuro-symbolic AI systems can achieve high benchmark accuracy via "Reasoning Shortcuts" — spurious, incorrect internal mappings that look right statistically but are wrong causally. The Three-Check Axiom Protocol in Section 5 is the direct architectural defence against this.

The PC algorithm on LLM activations is **scheduled for Month 3 as a research experiment only**. Production causal graph is seeded exclusively from verified ground-truth sources.

---

### 3.3 Module 3 — Working Memory

**Working Memory Specs:**
- Limits: 500 crystals per session, maximum 12 reasoning depth.
- Zero degradation: Any conclusion written at step N is retrieved at step M with perfect fidelity, unlike LLM attention windows which degrade across context.

**Why this beats LLMs on multi-step reasoning:**  
LLMs degrade by step 11 because attention distributes across the context window. Step 2 conclusion is overwritten by step 11 context. WorkingCrystal at step 2 is retrieved at step 12 with **perfect fidelity** because it is addressed, not attended to.

---

### 3.4 Module 4 — Simulation Engine

#### 3.4.1 The CRYSTAL Program Language — 16 Instructions

| Instruction | Arguments | Function |
|------------|-----------|----------|
| `LOAD <crystal_id>` | Crystal name/ID | Load crystal into working context |
| `BOND <source> <type>` | Source crystal, bond type | Follow bond, compound confidence |
| `COMPARE <a> <b>` | Two crystals | HDC similarity → context |
| `INFER <a> <b>` | Two crystals | Find most probable bond type |
| `NEGATE <crystal_id>` | Crystal | HDC NOT → search for closest match |
| `SEQUENCE [c1,c2,c3]` | Ordered crystals | Model causal/temporal chain |
| `INTERVENE <var> <val>` | Variable, new value | Pearl's do() — cut edges, set, recompute |
| `DERIVE <axiom> <inputs>` | Axiom, input crystals | First-principles derivation |
| `WRITE_WM <label> <crystal>` | Label, crystal | Write to working memory |
| `READ_WM <label>` | Label | Read from working memory, zero degradation |
| `ABSTRACT <crystals>` | Crystal list | HDC BUNDLE → superordinate category |
| `RETURN <crystal_or_key>` | What to return | End program, return answer |
| `ANALOGIZE <chain> <domain>` | Causal chain, target domain | Find structurally isomorphic chain in target domain |
| `FLOOD <crystal> <bond_type> <threshold>` | Crystal, bond type, min confidence | Follow ALL bonds above threshold simultaneously, return set |
| `ABSTRACT_LEVEL <crystals> <n>` | Crystal list, levels up | Ascend n abstraction levels via recursive BUNDLE |
| `META_REASON <trace>` | Reasoning trace | Analyze a reasoning trace for systematic patterns/failures |

**ANALOGIZE — Structural isomorphism discovery:**
The most powerful form of human reasoning is analogy — finding that two superficially 
different domains share deep structural similarity. HDC algebra makes this a 
mathematical operation:
**ANALOGIZE — Structural isomorphism discovery:**
Finds structure in target domain isomorphic to source chain via positional BIND HDC algebra. Enables cross-domain transfer of entire causal models (e.g. FACTORY to CELL).

This enables:
- "What is the biological equivalent of a factory?" → CELL
- "What in economics works like natural selection?" → MARKET_COMPETITION  
- "What is gravity in the social domain?" → HIERARCHY/POWER
- Cross-domain transfer of entire causal models, not just individual facts

#### 3.4.2 Four Reasoning Modes

```
# MODE 1: FORWARD SIMULATION
# Q: What are the consequences of deforestation?
LOAD deforestation
BOND deforestation precedes
WRITE_WM effect_1 current
SEQUENCE [deforestation, soil_erosion, flooding, ecosystem_collapse]
RETURN causal_chain

# MODE 2: BACKWARD INFERENCE  
# Q: Why did the Roman Empire fall?
LOAD roman_empire
BOND roman_empire caused-by
WRITE_WM cause_1 current
ABSTRACT [wm_cause_1, wm_cause_2]
RETURN collapse_causes

# MODE 3: COUNTERFACTUAL (Pearl's do-calculus)
# Q: What if Rome maintained its military?
LOAD roman_empire
LOAD military_strength
INTERVENE military_strength HIGH   # cuts incoming edges, sets HIGH, recomputes
DERIVE axiom_empire_stability [military_strength, economic_health]
RETURN counterfactual_trajectory

# MODE 4: ANALOGICAL (v4.3)
# Q: "What in biology works like a factory?"
LOAD factory
BOND factory part-of            # get factory substructure
WRITE_WM factory_model current
ANALOGIZE factory_model biology
RETURN current
# Returns: CELL — because input→processing→output→waste structure matches
```

---

### 3.5 Module 5 — Generative Composer (Revised v2.1)

> ⚠️ **GEMINI FINDING 1:** T5-small encoder-decoder is wrong for DSL synthesis. Its tokenizer generates `<UNK>` tokens on strict programmatic syntax, destroying CRYSTAL program validity.
>
> **GEMINI FINDING 2:** Phi-3 Q4_K_M quantization causes logic drift and hallucinated context injection. GBNF grammar constraints are mandatory.

**The two-stage revised architecture:**

#### Stage 1 — Program Synthesizer: Qwen2.5-Coder 0.5B

- Decoder-only architecture handles strict programmatic syntax without generating `<UNK>` tokens.
- Fine-tuned on Claude-generated (question, program) pairs.

#### Stage 2 — Structure Encoder: 60M parameter T5-small (t5-small)

- Input: raw simulation trace; Output: structured JSON.
- Narrow, well-defined task perfectly suited for T5-small.

#### Stage 3 — Expression Layer: Phi-3.8B Q4 with GBNF Constraints

- Mathematically prevents hallucinated context injection using GBNF grammar.
- Grammar rules strictly constrain output to register prefixes, core content, and valid source lists.

#### 3.5.1 Register System

| Register | When Used | Phi-3.8B instruction |
|---------|---------|---------------------|
| `conversational` | Default | Natural, accessible language |
| `formal` | Legal, medical, academic | Precise, citation-style |
| `poetic` | Creative, narrative queries | Evocative, structural expression |
| `technical` | Code, engineering | Key:value with types |
| `simple` | Accessibility | Short sentences, no jargon |

---

### 3.6 Module 6 — Pragmatic Reasoner

Theory of Mind implementation — computes **intended** meaning from **literal** content + context:

**Algorithm paths:**
1. **Irony:** If literal contradicts observable state AND speaker knows listener knows it → Intended meaning is negation of literal.
2. **Implication:** If cultural script implies more than literal → Intended meaning incorporates implied social protocol.
3. **Direct:** Fallback to literal interpretation.

#### Cultural Script Crystal Sets — v1

| Region | Key Script Differences | Detection Markers |
|--------|----------------------|------------------|
| Western European | Direct negation as irony. Understatement. | EN, FR, DE, NL |
| East Asian | Face-saving indirection. Agreement ≠ agreement. | ZH, JA, KO |
| South Asian | Elaborate politeness registers. | HI, BN, UR |
| Latin American | Hyperbole is non-ironic. Warmth intensifiers. | ES, PT-BR |
| Middle Eastern | Hospitality scripts. Formal indirect requests. | AR, FA, TR |

---

### 3.7 Module 7 — Epistemic Monitor

Computes confidence mechanically via four signals:
1. **Crystal coverage:** Fraction of query concepts present in library.
2. **Bond confidence:** Product of all bond scores in chain.
3. **Bounded logistic depth decay:** Deep chains decay smoothly, but high intermediate similarity (>0.90) shifts the decay midpoint rightward to protect strong chains.
4. **Working memory stability:** Consistency across referenced session concepts.

**Routing Thresholds:**
- `direct` (>= 0.90): Output answer without unconfident flags.
- `uncertain_flag` (>= 0.60): Output answer + UNCERTAIN warning.
- `explicit_unknown` (< 0.60): "I cannot answer this reliably."

---

### 3.8 Module 0 — Query Parser

> ⚠️ **v4.1 FIX:** This section was missing from v4.0. Without a query parser,
> Section 6 (Routing Flow) cannot start — "Parse: extract concept set + intent type"
> had no specification, no dataclass, no algorithm, and no code.

**Intent Categories & Patterns**:
- `counterfactual`: "what if", "had X not", "suppose"
- `causal`: "why", "because", "leads to"
- `creative`: "write", "imagine", "story"
- `pragmatic`: "really", "obviously", "of course"
- `temporal`: "before", "after", "during"
- `factual`: Default fallback.
- `novel`: Dynamically set if crystal coverage < 0.40.

---

### 3.8.5 Module 8 — Audit Logger (EU AI Act Article 12)

> ⚠️ **v4.1 FIX:** This module is SEPARATE from the Personal Layer AuditLog in
> Section 7.5. Module 8 is a system-level event logger, not user-data storage.
> It logs event types with HASHES, never raw queries. Required for EU AI Act
> Article 12 compliance: automatic logging for post-market surveillance.

**Specifications:**
- Backend: SQLite append-only with SHA-256 hash chain for tamper detection.
- Logged fields: event_type, query_hash, confidence, trace_hash, provenance, flags.
- Privacy: NEVER logs raw query text. Only hashes.

---

### 3.9 Error Handling & Retry Policy

> ⚠️ **v4.1 FIX:** No error handling was specified in v4.0. Without this,
> Claude Code will implement happy-path code that fails silently on:
> FAISS returning 0 results, invalid program synthesis, missing crystals,
> GBNF grammar deadlocks, and Working Memory overflow.

| Exception | Retry Policy |
|-----------|--------------|
| `ProgramSynthesisError` | 3 retries (T=0.1, 0.3, 0.5) → Fallback to explicit_unknown |
| `GrammarDeadlockError` | 3 retries with constraints → Output Raw JSON → Raise |
| `SimulationError` | Skip missing bond, log warning, confidence -15%. Never retry missing data. |
| `FAISS Empty Search` | Expand namespace (world→personal→axioms) → Return empty (coverage=0) |
| `WorkingMemoryFullError` | Trigger `COMPRESS` → Retry write. If still full, raise error. |

---

### 3.10 Module 9 — Public Interface

> ⚠️ **v4.1 FIX:** No API surface was specified in v4.0. Without this,
> Day 7 integration has no target to wire to. This defines exactly how
> users interact with CRYSTAL — both programmatically and via CLI.

| Method | Signature | Description |
|--------|-----------|-------------|
| `ask()` | `ask(question: str, register: str) -> CrystalResponse` | Main conversational loop |
| `inspect()` | `inspect(crystal_id: str) -> Crystal` | View raw vector + bonds |
| `edit()` | `edit(crystal_id: str, field: str, val) -> bool` | Edit specific crystal |
| `trace()` | `trace(question: str) -> SimulationTrace` | Return trace without language expression |

**CLI interface options:** `--trace`, `--register`, `--inspect`, `--benchmark`

---

### 3.11 Module 10 — Active Learning Engine (v4.2)

A new cognitive module that makes CRYSTAL a living system, not a static database.

**Web Search Integration:**
- CRYSTAL can search the web to answer questions outside crystal library coverage
- When Epistemic Monitor returns coverage < 0.40, the Active Learning Engine 
  triggers a web search instead of (or alongside) axiom derivation
- Search results are parsed, verified against existing crystals, and optionally 
  crystallized (converted to new crystals + bonds)
- MCP server integration for structured data sources (databases, APIs, knowledge bases)

**Self-Improvement Loop:**
- Continuous background process on cloud deployment
- Reads through existing crystal library looking for:
  - Missing connections (two crystals that SHOULD be bonded but aren't)
  - Contradictions (conflicting bonds from different sources)  
  - Stale knowledge (crystals with old timestamps, bonds from deprecated sources)
  - Weak spots (domains with low crystal density or connectivity)
- Proposes new bonds/crystals for human review or auto-accepts above confidence threshold
- Logs all changes to audit trail (Article 12 compliance maintained)

**Conversation Memory:**
- Cloud version maintains persistent memory across conversations
- Key conclusions from conversations become personal crystals
- Patterns across many conversations surface as candidate axioms
- User can inspect, edit, or delete any stored memory

---

## 4. THE GEMINI DEEP RESEARCH FIXES — FIVE FATAL BYPASSES

Gemini's deep research identified five implementation failures that would have killed the build in the first 72 hours. Every one is fixed here.

### 4.1 Fix 1 — SAE Mining: Use Gemma Scope, Not Custom Training

> **FATAL VULNERABILITY:** Training a custom SAE from scratch on Day 2 requires terabytes of activation data, multi-GPU clusters, weeks of optimization. Impossible on M1 in 24 hours. Conventional L1-penalty SAEs suffer from "shrinkage" — magnitude reconstruction errors. Training on 9B model requires 100+ TiB storage.

**THE FIX: Gemma Scope 2 + SAELens**

```bash
# Install SAELens — the standard library for loading pre-trained SAEs
pip install sae-lens

# Gemma Scope 2 has 30M+ pre-extracted features across all Gemma 3 and Gemma 2 layers
# Trained with JumpReLU (eliminates shrinkage) + Matryoshka (feature hierarchy)
# This replaces WEEKS of compute with a single Hugging Face download
```

**Summary of Fix:** Gemma Scope 2 has 30M+ pre-extracted features across all Gemma 3 and Gemma 2 layers. Trained with JumpReLU (eliminates shrinkage) + Matryoshka (feature hierarchy). This replaces WEEKS of compute with a single Hugging Face download.

**Feature Extraction Method:** For monosemanticity, feed the model `"Label: Description"` and extract features ONLY from the final token's residual stream.

**Version Upgrades:** Use Pairwise Dictionary Mean Correlation Coefficient (PW-MCC) to map features between SAE versions (e.g. v1 to v2). Flag shifts < 0.85 similarity for review.

---

### 4.2 Fix 2 — Wikidata: Offline Dumps, Not Live SPARQL

> **FATAL VULNERABILITY:** query.wikidata.org enforces 60-second query timeouts, 5 concurrent connections max, HTTP 429 throttling. In 2025-2026, Wikimedia executed a "Graph Split" — scholarly data moved to query-scholarly.wikidata.org. The main Blazegraph backend is in active crisis with 60-day reload times after corruption events.

**THE FIX: Local offline dumps**

```bash
# Step 1: Download Wikidata JSON dump (do this before Day 1 starts)
# WARNING: Full dump is 120GB compressed. Use the smaller truthy dump.
wget https://dumps.wikimedia.org/wikidatawiki/entities/latest-truthy.nt.bz2
# Truthy dump: ~8GB compressed, contains the most useful statements only

# Step 2: For ConceptNet — static download, no rate limits
wget https://s3.amazonaws.com/conceptnet/downloads/2019/edges/conceptnet-assertions-5.7.0.csv.gz
# ~1GB, contains all 21M edges

# Step 3: For ATOMIC 2020 — direct download
# From allenai.org/data/atomic-2020
# ~120MB, 1.33M if/then causal triples

# Step 4: Alternative endpoint for interactive SPARQL testing
# MillenniumDB: github.com/MillenniumDB/wikidata-endpoint
# No 60-second timeout. Full Wikidata. Use for development testing only.
```

**Summary of Fix:** Dump parses at ~50,000 statements/second on M1. Yields 500,000+ typed bonds in 2 hours offline without rate limiting. Requires building a QID→label mapping dict first, as truthy dump uses QIDs only (e.g. Q90).

---

### 4.3 Fix 3 — Program Synthesizer: Qwen2.5-Coder, Not T5-small

> **FATAL VULNERABILITY:** T5-small's tokenizer generates `<UNK>` tokens on strict DSL syntax. CRYSTAL programs have strict syntax (LOAD, BOND, INTERVENE, etc.) — `<UNK>` tokens cause silent execution failures.

| Model | Architecture | Params | DSL Fidelity | M1 Speed |
|-------|-------------|--------|-------------|----------|
| T5-Small | Encoder-Decoder | 60M | **Poor** — `<UNK>` on strict syntax | Fast |
| **Qwen2.5-Coder-0.5B** | **Decoder-Only** | **0.5B** | **Excellent** — built for code | **40+ tok/s** |
| Qwen2.5-Coder-1.5B | Decoder-Only | 1.5B | Excellent | 20+ tok/s |

```bash
# Download Qwen2.5-Coder 0.5B (Q8, ~550MB — fast, good quality)
huggingface-cli download Qwen/Qwen2.5-Coder-0.5B-Instruct-GGUF \
    qwen2.5-coder-0.5b-instruct-q8_0.gguf --local-dir data/models/
```

**Summary of Fix:** Generate 10,000 (question, program) pairs via Claude API, then LoRA fine-tune Qwen2.5-Coder. System prompt strictly limits output to the 16 valid `CRYSTAL` DSL instructions.

---

### 4.4 Fix 4 — Phi-3.8B: Grammar-Constrained Decoding is Mandatory

> **FATAL VULNERABILITY:** Q4_K_M quantization on Phi-3 reduces GSM8K accuracy from 0.825 (FP16) to ~0.720. More critically: quantized models drift from strict system prompts and inject hallucinated tokens to "fill conversational silences."

**THE FIX: GBNF Grammar Constraints via llama.cpp**

**Summary of Fix:** GBNF grammar strictly defines tokens the model can output (multi-paragraph text, specific source citations, rigid confidence format). Hallucination out of grammar is physically prevented during token selection.

---

### 4.5 Fix 5 — Vector Search: IVF Index Before Production

> **FATAL VULNERABILITY:** FAISS IndexBinaryFlat (brute-force exact search) degrades exponentially beyond 100,000 vectors. At 1M crystals, latency violates the sub-5ms target by orders of magnitude.

**Implementation:**

**Summary of Fix:** Train `faiss.IndexBinaryIVF` with `nlist = max(sqrt(N), 32)` and `nprobe=64`. Converts 80% RAM use while maintaining <5ms latency at 1M scale.

**Complete fix summary table:**

| PRD v3 Spec | Fatal Vulnerability | v4.0 Fix |
|------------|-------------------|---------|
| Train custom SAE on Day 2 | Requires 100+ TiB storage, weeks of GPU time | Load Gemma Scope 2 via SAELens — 4-hour download |
| Seed from Wikidata SPARQL | Rate limits, 60s timeouts, active backend crisis | Download truthy dump locally, parse offline |
| Fine-tune T5-small as synthesizer | `<UNK>` tokens destroy DSL syntax | Qwen2.5-Coder 0.5B — decoder-only, code-native |
| Use Phi-3 Q4 unconstrained | Logic drift, hallucinated context injection | GBNF grammar constraints via llama.cpp — mathematically enforced |
| FAISS IndexBinaryFlat for all search | Degrades exponentially past 100k vectors | IndexBinaryIVF with nprobe=64 for world library |

> ⚠️ **v4.1 FIX:** Additional fixes added in v4.1:

| v4.0 Spec | v4.1 Vulnerability Found | v4.1 Fix |
|-----------|-------------------------|----------|
| SAE from gemma-scope-2-27b | Cannot run on M1 32GB (~54GB VRAM needed) | Dual-profile: 9B for M1, 27B for Hetzner A100 |
| Wikidata parser uses tab-split | N-Triples format uses spaces, not tabs → 0 bonds | Regex-based N-Triples parser + QID→label mapping |
| No query parser specified | Routing cannot start without intent classification | Module 0 — QueryParser with 6 intent types |
| Fine-tune Qwen from GGUF | GGUF cannot be fine-tuned | LoRA on HF base model + merge + GGUF conversion |
| T5-small described as "15M params" | T5-small is 60.5M params | Corrected to 60M everywhere |
| No error handling specified | Happy-path code fails silently | CrystalError hierarchy + retry policies |
| No public API defined | No way to interact with CRYSTAL | CRYSTAL class + cli.py specification |
| Serialization via .pkl | Insecure, unstable, not human-readable | JSON + numpy .npy format |
| GBNF grammar single-line only | Prevents multi-paragraph answers | Multi-paragraph grammar with newlines |
| No audit logger (Article 12) | EU AI Act non-compliance | Module 8 — AuditLogger with hash chain |
| HDC dimension undocumented | Unclear why 2048 vs 8192/16384 | Explicit documentation + FAISS compatibility note |
| No structured logging | No observability during development | structlog with JSON output per module |
| No download verification | Downloads may fail silently | pre_flight_check.sh bash script |
| No pre-flight validation | Environment issues caught too late | pre_flight.py comprehensive checker |

---

## 5. AXIOM LAYER — FIRST PRINCIPLES DERIVATION

### 5.1 Why Axioms, Not More Crystals

When a user asks "What happens to fish if ocean temperature rises 5°C?", no crystal for this specific combination exists. The derivation engine computes the answer from biology axioms: temperature_affects_metabolism → reproduction_decline → habitat_range_shifts_poleward.

The answer is **derived**, not **retrieved**. The system flags it as derived, cites the axioms used, and reports honest confidence (0.71, not 0.97).

### 5.2 Axiom Sources — All Peer-Reviewed, All Free

| Source | Coverage | Size | Quality |
|--------|----------|------|---------|
| ConceptNet 5.7 | Commonsense, physical, social | 21M edges, ~1GB | Community + expert validated |
| WordNet 3.1 | Lexical, semantic hierarchy | 117k synsets, ~30MB | Princeton NLP — decades |
| OpenCyc | Formal logic, upper ontology | 239k assertions, ~80MB | Cycorp formal standard |
| ATOMIC 2020 | If/then social/physical causation | 1.33M triples, ~120MB | Allen AI — crowdsourced + validated |
| Wikidata (dump) | Factual causation, structured relations | Offline truthy dump | Wikimedia Foundation |

### 5.3 The Three-Check Axiom Protocol

Every candidate axiom must pass all three checks. This is what prevents Reasoning Shortcuts:

```
CHECK 1 — SOURCE:
  Appears in at least 2 of the 5 formal sources above?
  Pass: ConceptNet AND ATOMIC 2020 (two independent sources)
  Fail: Mark AXIOM_CANDIDATE, not AXIOM_VERIFIED

CHECK 2 — UNIVERSALITY:
  Holds in at least 3 unrelated domains?
  Example PASS: "High energy input causes state change"
    → holds in physics (melting), chemistry (reactions), economics (disruption)
  Example FAIL: "Hammers drive nails"
    → domain-specific heuristic, not a universal axiom

CHECK 3 — FALSIFIABILITY:
  Can you construct a concrete counterexample?
  If YES: it's a heuristic. Store as BOND, not AXIOM.
  If NO:  it's a genuine first principle. Mark AXIOM_VERIFIED.

RESULT: ~2,000 AXIOM_VERIFIED from ~50,000 candidates
        ~12,000 AXIOM_CANDIDATE (hedged derivations only)
```

### 5.4 Derivation Engine

**Derivation Engine Core Logic:**
Navigates verified logic rules (axioms) up to MAX_DEPTH=6. Calculates confidence using Bounded Logistic Decay based on chain length and subset similarity. Always flags answer as derived.

---

## 6. COMPLETE QUERY ROUTING FLOW

```
QUERY RECEIVED
  → Parse: extract concept set + intent type
      intents: factual | causal | counterfactual | creative | pragmatic | novel

  → Epistemic Monitor PRE-FLIGHT:
      coverage < 0.40  → DERIVATION ENGINE (axiom-based computation)
      coverage 0.40-0.70 → HYBRID: crystal + derivation
      coverage > 0.70  → CRYSTAL + CAUSAL SIMULATION

  → Working Memory: load session context

  → Program Synthesizer (Qwen2.5-Coder 0.5B):
      generate causal program from intent + context

  → Simulation Engine: execute program
      factual        → crystal lookup + bond traversal
      causal         → causal graph simulation (fwd or bwd)
      counterfactual → INTERVENE operator + re-simulation
      creative       → narrative causal simulation + Generative Composer
      pragmatic      → Pragmatic Reasoner + cultural script
      novel          → Axiom Layer + Derivation Engine

  → Meta-Reasoning Monitor:
      chain_depth > 8:         trigger ABSTRACT (zoom out one level)
      confidence drop > 5%/step: trigger PIVOT (change strategy)
      working_memory > 400:    trigger COMPRESS (summarise context)

  → Epistemic Monitor POST-FLIGHT:
      confidence > 0.90  → answer directly
      confidence 0.60-0.90 → answer + UNCERTAIN flag
      confidence < 0.60  → answer + UNCERTAIN + full derivation shown
      coverage_miss ≠ [] → always list missing crystals explicitly

  → Structure Encoder (60M T5-small):
      simulation trace → structured JSON

  → Phi-3.8B Q4 + GBNF grammar:
      JSON → natural language in specified register

  → Working Memory: write intermediate conclusions
  → RETURN: answer + confidence + full trace + provenance
```

---

## 7. SAFETY ARCHITECTURE

### 7.1 Five Structural Safety Properties — Cannot Be Disabled

```
1. EPISTEMIC HONESTY
   Confidence computed from 4 mechanical signals.
   No user input path to the confidence calculation.
   False confidence is architecturally impossible.

2. TRACEABLE PROVENANCE
   Every answer returns crystal sources + derivation chain.
   No answer without showing how it was reached.
   Opacity is architecturally impossible.

3. BOUNDED SELF-MODIFICATION
   Personal crystals update at 0.5% per interaction (EMA).
   No mechanism for rapid belief rewriting.
   No path to runaway self-modification.

4. EXPLICIT KNOWLEDGE BOUNDARIES
   Coverage miss is always reported.
   Cannot confidently answer outside crystal coverage.
   Hallucination on covered queries: architecturally impossible.

5. NO LATENT OPTIMISATION
   No objective function during inference.
   CRYSTAL simulates. It does not pursue goals.
   No instrumental convergence risk.
```

### 7.2 Personal Layer Privacy — Zero Exceptions

```
1. AES-256 encryption with device-local key at rest.
2. Device-local key never leaves the device.
3. No server-side API can read, write, or access personal crystals.
4. usr_ prefix enforced at data model level on every write.
5. World library read-only after release. No personal→world write path.
6. On uninstall: cryptographic wipe, not delete.
7. Personal crystal vectors never in telemetry, logs, or analytics.
8. Cross-device sync: explicit user-initiated export, user-controlled password.
```

### 7.3 EU AI Act Compliance (Gemini Research Finding)

> **GEMINI FINDING:** EU AI Act high-risk AI provisions become fully enforceable **August 2026**. High-risk systems (healthcare, legal, employment, education, critical infrastructure) require legally binding Article 13 transparency, explainability, and error traceability. Black-box LLMs deploying in these sectors face market exclusion and heavy fines.

CRYSTAL's response: **compliance is an architectural property, not a compliance task.**

| EU AI Act Requirement | CRYSTAL's Built-in Response |
|-----------------------|---------------------------|
| Article 13: Transparency | Full simulation trace returned with every answer |
| Explainability mandate | Crystal provenance + bond citations on every answer |
| Error traceability | UNCERTAIN flags + derivation chains logged automatically |
| GDPR data minimisation | Personal crystals never leave device, AES-256 |
| Right to explanation | Trace shows exact causal logic in human-readable form |
| Human oversight | Confidence < 0.60 explicitly flags uncertainty to the user |
| Article 12: Automatic logging | Encrypted append-only SQLite audit log records all UNCERTAIN/BLOCKED queries with hash chain (Section 7.5) + system-level AuditLogger (Section 3.8.5) |

**Strategic position:** As LLMs are legally excluded from regulated sectors, CRYSTAL is the natural replacement. This is not a compliance burden — it is the product.

### 7.4 Crystal-Level Harm Detection

```python
class HarmMonitor:
    BLOCKED_DOMAINS = [
        'weapons_synthesis', 'child_exploitation',
        'mass_casualty_methods', 'surveillance_tools',
        'identity_fraud', 'financial_manipulation',
    ]

    def check_program(self, program: list[str]) -> HarmAssessment:
        for instruction in program:
            crystals = self._extract_crystal_refs(instruction)
            for cid in crystals:
                crystal = self.store.get(cid)
                if crystal and any(d in crystal.domain for d in self.BLOCKED_DOMAINS):
                    return HarmAssessment(blocked=True, reason=f'{cid} in blocked domain')
        return HarmAssessment(blocked=False)

    # KEY: harm detection at CRYSTAL level, not TEXT level
    # An adversarial paraphrase of a harmful query activates the SAME crystals
    # The block triggers regardless of surface phrasing — adversarial paraphrase fails
```

### 7.5 Article 12 Compliance — Encrypted Append-Only Audit Log

> **EU AI Act Article 12** requires automatic logging of AI system operation for the entire lifetime of the system, enabling post-market surveillance and incident investigation. Logs must be tamper-resistant, traceable, and retained for a period appropriate to the intended purpose.

CRYSTAL implements this via an **encrypted, append-only SQLite log** in the Personal Layer. All queries routed to `uncertain_flag` or `blocked` by the Epistemic Monitor or Harm Monitor are automatically recorded with a cryptographic hash chain for tamper detection.

**AuditLog Specifications:**
- Uses Fernet (AES-128-CBC) with device-local key.
- Creates `audit_log` SQLite table with full chain hash `SHA-256(previous_hash + current_row)`
- Integrates with Epistemic Monitor & Harm Monitor automatically.

**Privacy guarantees:**
1. Simulation traces are Fernet-encrypted with the device-local key before storage.
2. Only the query SHA-256 hash is stored unencrypted — the original query text is not retained.
3. The audit log lives in the Personal Layer — same AES-256 protection, same device-local scope.
4. On uninstall: cryptographic wipe covers the audit log alongside personal crystals.
5. Hash chain enables tamper detection without exposing content to external auditors.

---

## 8. THE FIVE PROPERTIES IMPLEMENTATION ROADMAP

> ⚠️ **v4.3:** This section documents the engineering path from the five properties
> defined in Section 1.3 to working modules.

### 8.1 Property 1 — Generative (Axiom Composition)

The DerivationEngine exists but contains zero axioms. Axiom seeding plan:

**Source 1:** Extract from ConceptNet. Patterns like "X causes Y" that appear across 
3+ unrelated domains become axiom candidates. "Heat causes state change" appears in 
physics, chemistry, cooking, geology — verified universal principle.

**Source 2:** Extract from ATOMIC 2020. If/then causal rules that survive the 
Three-Check Protocol.

**Source 3:** MDL discovery. When the Compression Engine finds a single rule that 
generates 50+ bonds, that rule is an axiom candidate.

**Composition mechanism:** Given axioms A1: "heat → state_change" and A2: "ice = 
solid_water" and A3: "liquid is a state", the DerivationEngine chains: 
heat + ice → state_change(solid_water) → liquid_water. Three axioms, one derivation, 
zero lookup. This IS Property 1.

### 8.2 Property 2 — Compact (Compression Engine)

New module: CompressionEngine.

```python
class CompressionEngine:
    def compress_cycle(self, crystal_store, bond_store, axiom_store):
        """One compression cycle. Run periodically or during Dream Phase 2."""
        # Step 1: Find bond clusters — groups of bonds sharing structural pattern
        # Example: (X, instance-of, ANIMAL) for X in {DOG, CAT, HORSE, ...}
        clusters = self._find_structural_clusters(bond_store)
        
        # Step 2: For each cluster, formulate a candidate axiom
        # "domesticated_mammal → instance-of → ANIMAL" (covers 50 bonds)
        candidates = [self._cluster_to_axiom(c) for c in clusters]
        
        # Step 3: Verify — can the axiom reproduce ALL bonds in the cluster?
        verified = [a for a in candidates 
                    if self._verify_reproduction(a, bond_store)]
        
        # Step 4: For verified axioms — compute compression ratio
        # ratio = bonds_explained / axiom_description_length
        # Higher ratio = deeper understanding
        for axiom in verified:
            axiom.compression_ratio = self._compute_ratio(axiom)
        
        # Step 5: Accept axioms above threshold
        # DO NOT delete bonds yet — mark them as "derivable"
        # Deletion happens only after human review or 30-day verification period
        
        # Step 6: Report understanding_depth metric
        total = len(bond_store)
        derivable = len([b for b in bond_store if b.derivable_from_axiom])
        understanding_depth = derivable / total if total > 0 else 0
        return understanding_depth
```

`understanding_depth` is the CORE metric of CRYSTAL.
It measures what fraction of knowledge is UNDERSTOOD vs merely STORED.
Target: 0.0 at launch → 0.3 at month 3 → 0.5+ at year 1

### 8.3 Property 3 — Compositional (DSL Library Learning)

Inspired by DreamCoder (Ellis et al., 2021). The system discovers reusable 
reasoning patterns from its own DSL execution history.

After every successful query:
1. Log the CRYSTAL program that produced the correct answer
2. Every 1000 programs: analyze for repeated sub-sequences
3. Common sub-sequences become named macros:
   ```
   CATEGORIZE(X) = LOAD X → BOND X instance-of → WRITE_WM cat → BOND current instance-of → RETURN
   CAUSE_CHAIN(X) = LOAD X → BOND X caused-by → WRITE_WM c1 → BOND current caused-by → RETURN
   ```
4. Macros are added to the DSL as new instructions
5. The synthesizer learns to emit macros instead of raw instructions
6. Higher-order macros compose lower-order macros

This is how the system's COGNITIVE VOCABULARY grows over time.

### 8.4 Property 4 — Causally Correct (Interventional Verification)

Already built: CausalModel + INTERVENE operator.
Missing: systematic verification loop.

Every unverified bond gets tested:
1. INTERVENE source HIGH → does target change? 
2. INTERVENE target HIGH → does source change?
3. If (1) yes and (2) no → causal direction confirmed: source → target
4. If both change → confound exists, mark bond as "correlational, not causal"
5. Results feed into Epistemic Monitor confidence scores

### 8.5 Module 11 — Dream Engine

**Interface Spec:** Offline discovery, consolidation, and pruning run during idle periods. Phase 1 (REM) generates random walks to find coherent paths. Phase 2 (Deep sleep) consolidates bond confidences. Phase 3 (Pruning) removes dead weight.

### 8.6 Two Deployment Modes (Expanded)

**Cloud Intelligence (maximum reasoning):**
- Full crystal library, full bond graph, full axiom store
- Always online — web search, MCP servers, API access
- Dream Engine runs continuously during idle
- Compression Engine optimizes understanding depth
- Self-play training: accumulates (query, program, result) triples, 
  periodically retrains synthesizer via LoRA
- Persistent conversation memory across sessions
- Target: maximum understanding_depth, unlimited growth

**Edge Intelligence (compressed, portable):**
- Top N crystals by connectivity + their bonds (configurable N)
- All verified axioms (small — axioms compress knowledge)
- Fully offline — airplane mode reasoning with full traces
- No Dream Engine, no Compression Engine (cloud does this)
- Syncs new axioms + crystals from cloud when online
- Target: < 1GB core, < 3.5GB full, fits on phone

### 8.7 Inference-Time Compute Scaling (MCTS over Reasoning Programs)

For hard queries, the system does not generate one program. It generates many, 
evaluates them, and refines the best:

1. Synthesizer generates 10 candidate CRYSTAL programs (temperature=0.8)
2. Simulation Engine executes all 10 in parallel (~2ms total)
3. Epistemic Monitor scores each result
4. Top 3 candidates enter refinement: synthesizer generates deeper programs 
   that extend the best candidates
5. Repeat 2-3 times (tree search over reasoning space)
6. Return the highest-confidence result with full trace of all attempts

This is Monte Carlo Tree Search over CRYSTAL's DSL — the same principle as AlphaGo, applied to reasoning programs instead of board positions.

### 8.8 Self-Improvement Training Loop

The cloud deployment accumulates training signal from every interaction:

1. Correct answers → (question, program, answer) saved as positive training examples
2. Incorrect answers → error analysis → targeted web search or axiom refinement
3. Every 10,000 interactions: LoRA fine-tune synthesizer on accumulated data
4. Every compression cycle: evaluate understanding_depth metric
5. understanding_depth is the SINGLE north star metric

### 8.9 Analogy Engine — Cross-Domain Structural Reasoning

Analogy is not a feature. It is arguably the core mechanism of human intelligence 
(Hofstadter, 2001). Every scientific breakthrough is an analogy: "the atom IS a solar 
system," "DNA IS a code," "the brain IS a computer." Each maps causal structure from 
a known domain onto an unknown one.

CRYSTAL's HDC algebra enables analogy as a first-class operation:

**Pair analogy (word2vec-style but over causal graphs):**
```
A:B :: C:?
relationship = BIND(A_hdc, B_hdc)
answer_hdc = UNBIND(relationship, C_hdc)
? = search(answer_hdc, crystal_store)
KING:QUEEN :: MAN:? → WOMAN (relationship = "gender_counterpart")
```

**Chain analogy (structural isomorphism):**
```
source_chain: A --causes--> B --enables--> C --produces--> D
target_chain: ? --causes--> ? --enables--> ? --produces--> ?
Encode structure as: BIND(bond_type_1, BIND(bond_type_2, bond_type_3))
This captures the PATTERN independent of content.
Search for chains in target domain with same bond-type sequence.
Rank by HDC similarity of corresponding crystal pairs.
```

**Whole-model analogy (the breakthrough capability):**
```
source_model: entire causal subgraph around concept X
target_model: find the most isomorphic subgraph in domain Y
Method:
  1. Extract N-hop neighborhood of source concept as a subgraph
  2. Encode subgraph structure: for each path, BIND(node_vectors, edge_types)
  3. BUNDLE all path encodings → single "model signature" vector
  4. For each crystal in target domain: extract same N-hop neighborhood
  5. Encode and compare model signatures
  6. Highest similarity = best analogy
```

This finds deep structural analogies that no keyword or embedding search can find.

**Integration with Dream Engine:** During REM phase random walks, when a walk 
discovers high coherence between two distant crystals, the Analogy Engine checks 
whether the PATH between them is structurally isomorphic to known causal patterns. 
Dreams become a source of analogical discovery.

### 8.10 Emergent Abstraction Hierarchy

Knowledge is not flat. Reality is organized in layers where each layer has 
its own causal rules that cannot be reduced to the layer below:

```
Layer 0: Raw crystals       (WATER, DOG, PARIS, OXYGEN)
Layer 1: Categories          (LIQUID, ANIMAL, CITY, ELEMENT)
Layer 2: Principles          (CONSERVATION, ADAPTATION, GOVERNANCE)
Layer 3: Meta-principles     (SYMMETRY, EQUILIBRIUM, EMERGENCE)
Layer 4: Foundational        (INVARIANCE, INFORMATION, CAUSATION)
```

**These layers are NOT manually defined.** They EMERGE from compression:

**Interface Spec:** Abstraction is discovered via recursive compression. Finds axiom structural clusters → shared structure becomes new concept (`BUNDLE`) at Layer N+1.

**Why this matters:** A system that only has Layer 0 can answer "what is the 
capital of France." A system with Layer 2 can answer "why do empires fall" 
(by applying GOVERNANCE principles). A system with Layer 3 can answer "what do 
biological evolution and market competition have in common" (both are instances 
of EVOLUTIONARY_PROCESS). A system with Layer 4 can reason about the nature of 
causation itself.

**Measurement:** `abstraction_depth` = highest non-empty layer. 
Target: Layer 2 by month 6. Layer 3 by year 1.

### 8.11 Evolving Domain-Specific Reasoning Languages

The 16 DSL instructions are a starting vocabulary. But the optimal reasoning 
language for quantum physics is different from the optimal language for history 
is different from the optimal language for ethics.

**The system evolves domain-specific DSLs through genetic programming:**

**Stage 1 — Observation:** Log every successful CRYSTAL program with its domain tag.
After 10,000 programs: analyze which instruction sequences appear only in specific 
domains.

**Stage 2 — Macro extraction:** Common domain-specific sequences become named macros.
Physics programs frequently use: `LOAD → INTERVENE → BOND caused-by → COMPARE`
This becomes: `SIMULATE_EFFECT(concept, intervention)` — one macro replacing four 
instructions.

**Stage 3 — Mutation:** Programmatically generate NOVEL instructions by modifying 
existing ones:
- `BOND` follows one edge → `FLOOD` follows all edges above threshold
- `COMPARE` measures two crystals → `SPECTRUM` measures a crystal against N reference points
- `DERIVE` applies one axiom → `CASCADE` applies all applicable axioms recursively
- `NEGATE` flips one crystal → `INVERT` reverses an entire causal chain

**Stage 4 — Selection:** Test mutated instructions on held-out queries per domain.
Instructions that improve accuracy survive. Others are pruned.

**Stage 5 — Speciation:** After sufficient evolution, each domain has its own DSL dialect:

```
Physics-DSL:    SIMULATE_CONTINUOUS, CONSERVE, SYMMETRY_CHECK, FIELD_PROPAGATE
History-DSL:    TIMELINE, COUNTERFACTUAL_BRANCH, MOTIVATE_AGENT, POWER_DYNAMICS
Biology-DSL:    EVOLVE, NICHE_PRESSURE, ECOSYSTEM_BALANCE, GENE_EXPRESSION
Ethics-DSL:     STAKEHOLDER_MAP, CONSEQUENCE_CHAIN, PRINCIPLE_TEST, CONFLICT_RESOLVE
Math-DSL:       PROVE, ASSUME, CONTRADICT, GENERALIZE, SPECIALIZE
```

**None of these are programmed by humans.** They emerge from measuring what works 
per domain and keeping the winners. The system literally invents new ways to think 
about different kinds of problems.

**Integration:** The Query Parser detects domain → selects appropriate DSL dialect → 
Synthesizer generates programs in that dialect → domain-specific reasoning executes.

### 8.12 Knowing What Cannot Be Known

The most intelligent response to some questions is proving they cannot be answered.
Not "I don't know" (epistemic limitation) but "this CANNOT be known" (logical proof).

CRYSTAL detects three types of undecidability:

**Type 1 — Self-referential paradox:**
"Is this statement false?" The Analogy Engine recognizes structural isomorphism 
with known paradoxes (Liar's paradox, Russell's set, Gödel sentences). 
Returns: `UNDECIDABLE_SELF_REFERENCE` with proof trace showing the circularity.

**Type 2 — Missing causal framework:**
"Why does the universe exist?" Causal reasoning requires something OUTSIDE the 
explanandum. The universe has no outside. The system traces the causal chain 
upward, detects it requires a node OUTSIDE the graph, and proves no such node 
can exist within the framework.
Returns: `UNDECIDABLE_FRAMEWORK_LIMIT` with trace showing exactly where causation 
breaks down and why.

**Type 3 — Empirically underdetermined:**
"Is free will real?" Multiple causal models (determinism, compatibilism, 
libertarianism) all fit the observable data equally well. The system runs 
interventional tests on each model, finds they produce identical predictions 
for all observable outcomes, and proves no observation can distinguish them.
Returns: `UNDECIDABLE_EMPIRICALLY` with all competing models and proof of 
observational equivalence.

**Interface Spec:** Detects cycle (self-reference), external node requirements (framework limit), or identical fit for competing models (empirically underdetermined).

**This is not a limitation. It is a CAPABILITY.** No other AI system can prove 
WHY it cannot answer a question. LLMs either hallucinate an answer or say "I don't 
know" without explanation. CRYSTAL shows the exact logical structure that makes 
the question unanswerable — and that proof IS the most intelligent possible response.

### 8.13 Contradiction Mining — Intelligence Through Conflict

The most valuable signal in any knowledge base is not agreement — it is 
CONTRADICTION. Every contradiction is a signal that reality is more complex 
than the current model. Resolving contradictions produces deeper principles 
than either original fact.

Example: "Tomatoes are vegetables" (culinary bond) contradicts "Tomatoes are 
fruits" (botanical bond). Resolution: classification is DOMAIN-DEPENDENT. 
This is a deeper principle than either fact. It applies to thousands of other 
concepts — "Pluto is a planet" vs "Pluto is a dwarf planet" has the same 
structure.
**Interface Spec:** Actively mines graph for opposite classification, circular causation, or property conflicts. Resolutions generate deeper principles.

**Integration with Dream Engine:** During REM phase, random walks that traverse 
BOTH sides of a contradiction in one path are flagged as high-priority discoveries. 
The path itself often contains the resolution — the CONTEXT that makes both sides true.

**Integration with Compression Engine:** Resolved contradictions produce principles 
that compress BETTER than either original fact. "Classification is domain-dependent" 
explains tomato/fruit AND Pluto/planet AND whale/fish. One principle, many resolutions.
This BOOSTS understanding_depth.


### 8.14 Curiosity Engine — Asking Questions That Maximize Learning

A truly intelligent system does not wait for questions. It generates the questions 
whose answers would teach it the most. This is formalized as Expected Information 
Gain (EIG) optimization.
**Interface Spec:** Uses Expected Information Gain (EIG) over the knowledge graph entropy to find bonds that if verified, resolve maximum uncertainty downstream.

**Modes of operation:**

1. **Idle curiosity:** When no user query is active, generate top-10 questions and 
   attempt to answer them via web search / MCP. Every self-answered question makes 
   the system smarter without human input.

2. **Dialogue curiosity:** When talking to a user about a topic, generate 
   follow-up questions that would deepen understanding of THAT topic. 
   "You asked about climate change. I'd also like to know: does ocean 
   acidification affect coral reef calcium formation? That would connect 
   three uncertain areas in my knowledge."

3. **Strategic curiosity:** Before a benchmark or evaluation, identify the 
   questions most likely to improve accuracy, and prioritize learning those first.


### 8.15 Adversarial Self-Debate — Internal Peer Review

No answer should leave the system without surviving internal challenge.
This is the scientific method's peer review, internalized.
**Interface Spec:** Auto-spawns an opponent agent to actively disprove the proposed answer. Survived attacks boost confidence, successful ones trigger re-derivation.

**Trace output example:**
Q: "What causes fire?"
Round 0:
ANSWER: spark (conf: 0.77)
ATTACK: "Oxygen is also required — spark without oxygen produces no fire" (conf: 0.65)
DEFEND: "Spark is the TRIGGER cause. Oxygen is a PRECONDITION. Both are correct
but spark answers the question of WHAT INITIATES fire." (conf: 0.72)
RESULT: Original answer holds, confidence boosted to 0.82
Round 1:
ATTACK: "Lightning causes more fires globally than sparks" (conf: 0.40)
DEFEND: "Lightning IS a type of spark (electrical discharge). The answer
generalizes correctly." (conf: 0.68)
RESULT: Original answer holds, confidence boosted to 0.85
Final: spark (conf: 0.85, survived 2/2 rounds)

**This trace is the DEMO KILLER.** No other AI shows you the internal debate. 
Users can see the system challenge itself, defend its reasoning, and arrive at a 
stronger answer BECAUSE it tried to disprove itself.


### 8.16 Perspective Simulation — Multi-DSL Synthesis

The same question viewed through different reasoning frameworks yields different 
but complementary insights. Perspective Simulation runs a query through multiple 
domain-DSLs and synthesizes across viewpoints.
**Interface Spec:** Synthesizes answer traces generated by multiple distinct domain-DSLs. Looks for cross-domain structural isomorphism to propose Layer 3+ meta-principles.


### 8.17 Negative Knowledge — Explicit Falsehoods

What a system knows is NOT true is as valuable as what it knows IS true. 
Negative knowledge prevents reasoning errors that positive knowledge alone cannot catch.
**Interface Spec:** Explicitly stored NOT-relationships with structural REASONS attached. Prevents recurrent logic traps.

**Sources of negative knowledge:**

1. **Contradiction resolution:** When ContradictionMiner resolves "A is B" vs 
   "A is NOT B", the losing side becomes a NegativeBond with the resolution as reason.

2. **Adversarial debate:** When self-debate disproves a candidate answer, the 
   disproved claim becomes a NegativeBond. Future queries won't re-derive it.

3. **Dream discovery:** When random walks find high semantic similarity between 
   two crystals with NO connecting bonds, the Curiosity Engine investigates. 
   If investigation confirms they SHOULD NOT be connected, create a NegativeBond.
   "WHALE and FISH are semantically similar (0.72) but explicitly NOT related 
   because [reason]."

4. **User correction:** When a user says "that's wrong," the corrected claim 
   becomes a NegativeBond. The system cannot make the same mistake again.

**Integration with Simulator:**
Before returning any answer, check if the proposed bond exists as a NegativeBond. 
If yes: skip it, use the reason to find a BETTER answer, and include the negative 
knowledge in the trace: "Note: WHALE is NOT a fish (despite semantic similarity 0.72) 
because [reason]. Correct classification: MAMMAL."

**Integration with Epistemic Monitor:**
Answers that avoid known NegativeBonds get a confidence BOOST — the system 
navigated a known trap correctly.


### 8.18 Temporal Simulation — Reasoning Over Time

Static reasoning answers "what is X?" Dynamic reasoning answers "what happens to X 
over time?" This requires propagating state changes through causal bonds step by step.
**Interface Spec:** Propagates state variables across time steps, triggering phase transitions defined in the Axiom Store when thresholds are met.

**New DSL instructions for temporal reasoning:**

| `SET_ATTRIBUTE <crystal> <attr> <value>` | Crystal, attribute name, numeric value | Set a numeric attribute on a crystal |
| `SIMULATE_FORWARD <crystal> <attr> <steps>` | Crystal, attribute, time steps | Propagate state changes forward in time |
| `TIMELINE <crystals>` | List of crystals | Show temporal evolution of multiple crystals in parallel |

### 8.19 Knowledge Scale Architecture — From Axioms to All Human Knowledge

CRYSTAL's knowledge exists in four concentric tiers, each compressing the tier 
below it:

**Tier 1 — Axiom Core (~5 GB)**
Universal principles that are true across all domains. "Conservation laws constrain 
state changes." "Complex systems collapse when maintenance exceeds regeneration." 
"Classification is domain-dependent." Approximately 50,000 verified axioms + 
meta-principles across 5 abstraction layers. This tier alone enables derivation of 
~40% of factual questions via principle composition.

**Tier 2 — Structural Knowledge (~50 GB)**  
All entities that matter: every country, city, species, element, historical event, 
scientific concept, cultural artifact. Approximately 10M crystals with 50M bonds.
Packed binary: 256 bytes per crystal, ~100 bytes per bond. This is the world's 
factual skeleton — what connects to what, and how.

**Tier 3 — Domain Depth (~200 GB)**
Specialized knowledge per domain: medical literature compressed to causal structures, 
legal precedent networks, engineering specifications, biological pathways. Each domain 
is a dense subgraph that connects to the Tier 2 skeleton. Approximately 100M domain-
specific bonds across 50 domains.

**Tier 4 — Living Layer (grows continuously)**
Real-time knowledge from web search, MCP integrations, conversations, and Dream Engine 
discoveries. This tier is never complete — it grows, gets compressed into higher tiers 
via the Compression Engine, and eventually its best patterns become Tier 1 axioms.

**Total structured human knowledge estimate: ~350-500 GB**

For comparison: GPT-4's weights alone are ~1.8 TB and cannot explain any of their 
content. CRYSTAL at 500 GB contains MORE accessible knowledge — every piece traceable, 
editable, and derivable.

**Hardware requirement: one server.** 2TB NVMe, 256GB RAM, one A100 GPU.
Cost: ~€200/month. Not a datacenter. Not a cluster. One machine.

#### Deployment Distribution

| Tier | Cloud | Phone | What it enables |
|------|-------|-------|----------------|
| Tier 1 (Axioms) | Full | Full (~5 GB) | Derivation from principles — answers most "why" questions |
| Tier 2 (Structure) | Full | Hot cache (~2 GB, personalized top 50K crystals) | Factual answers — "what is the capital of X" |
| Tier 3 (Domains) | Full | User's domains only (~1-3 GB) | Deep expertise in YOUR fields |
| Tier 4 (Living) | Full | Sync on connect | Latest knowledge, real-time updates |
| **Total** | **~500 GB** | **~8-12 GB** | Cloud: omniscient. Phone: personal genius. |

The phone carries ~2% of total knowledge but can answer ~80% of questions because 
Tier 1 axioms enable derivation. The remaining 20% triggers an MCP query when online, 
or returns honest uncertainty when offline.

#### The Compression Flywheel

The system gets SMALLER as it gets SMARTER:
Year 1: 10M crystals, 50M bonds, 500 axioms
understanding_depth: 0.15
Storage: 80 GB
Year 2: 10M crystals, 50M bonds, 2,000 axioms
understanding_depth: 0.50
Storage: 60 GB (half the bonds are now derivable and compressed)
Year 5: 10M crystals, 50M bonds, 10,000 axioms
understanding_depth: 0.80
Storage: 30 GB (80% of bonds replaced by axioms)
Phone: 10 GB carries 90% of answerable questions

This is the opposite of every other AI system. Traditional AI grows linearly with 
knowledge. CRYSTAL grows logarithmically — deeper understanding means better 
compression means less storage for more capability.

### 8.20 MCP-Native Architecture — CRYSTAL as a First-Class Internet Citizen

The current internet is unstructured text behind HTML pages. You search, get 10 blue 
links, read them yourself, extract meaning manually. This is ending.

MCP (Model Context Protocol) transforms every database, API, and knowledge base into 
a structured, machine-readable service. Instead of "search Google for Tokyo population", 
the system sends a typed query to a specific MCP server: 
`wikidata_mcp.query(entity="Tokyo", property="population", year=2025)` and gets back 
a structured, verified, citable response.

CRYSTAL is architecturally designed for this world:

#### Offline Mode (no network)
Query → QueryParser → Synthesizer → Simulation over local crystals/bonds/axioms
→ If confidence > threshold: return answer with trace
→ If confidence < threshold: return "I'm uncertain, here's what I can derive
from principles, and here's exactly what I'd need to look up to be sure:
[specific MCP query that would resolve the uncertainty]"

The system doesn't just say "I don't know." It tells you EXACTLY what it would 
need to know and WHERE it would look. When you reconnect, those queries are 
ready to fire.

#### Online Mode (MCP connected)
Query → QueryParser → Epistemic Monitor pre-flight
→ If coverage > 0.70: answer from local knowledge (fastest)
→ If coverage 0.40-0.70: answer from local + verify via MCP
→ If coverage < 0.40:

Curiosity Engine formulates the PRECISE question to ask
Active Learning Engine selects the RIGHT MCP server:

Factual entity? → Wikidata MCP
Medical? → PubMed MCP
Legal? → Court records MCP
Code? → GitHub MCP
News? → Reuters MCP
Product? → Manufacturer MCP


Query is sent, response received
Response is VERIFIED against existing knowledge graph
(does it contradict known facts? is the source reliable?)
If verified: crystallize (create new crystals + bonds)
Answer returned with provenance: "From [MCP source], verified
against [N existing bonds], confidence [X]"


#### Crystallization — Learning from MCP responses
Every MCP response that passes verification becomes permanent knowledge:
1. New entity? → Create crystal, encode with sentence-transformers, binarize
2. New relation? → Create bond with provenance="mcp_{server_name}"
3. Confirms existing bond? → Boost confidence (cross-referencing)
4. Contradicts existing bond? → Flag for ContradictionMiner
5. Next time the same question is asked: answer from local, no MCP needed

The system LEARNS from every query. After 10,000 MCP interactions, the phone's 
hot cache has been shaped by real usage into a personalized knowledge base that 
answers 95% of YOUR questions without network access.

#### MCP Server Discovery
CRYSTAL maintains a registry of known MCP servers with:
- Domain coverage (what kind of questions can this server answer?)
- Reliability score (how often do its responses verify against known facts?)
- Latency profile (how fast does it respond?)
- Cost (some MCPs may charge per query)

The Curiosity Engine doesn't just pick any MCP — it picks the one with the 
highest expected information gain per unit cost. A free, reliable MCP with 
broad coverage is preferred over a paid, narrow one — unless the specific 
question falls exactly in the narrow one's domain.

#### The End State
A phone running CRYSTAL in 2030:
- Offline: answers 90% of questions from compressed axioms + personal cache
- Online: the remaining 10% answered in <500ms via targeted MCP query
- Every answer: full trace, editable, confidence-scored
- Every MCP interaction: learned, crystallized, never repeated
- The more you use it: the less it needs the network
- The less it needs the network: the more private it becomes
- The more private: the more people trust it with real questions

This is not a search engine. It's not an assistant. It's a personal 
intelligence that grows with you, reasons from principles, and only reaches 
out to the network when it genuinely needs to — and tells you exactly why.

---

## 9. TEN-YEAR EDGE CASE REGISTER

### 9.1 Technical Edge Cases

| Edge Case | Failure Without Fix | Fix |
|-----------|-------------------|-----|
| Polysemy (BANK = 9 meanings) | Wrong sense in 8 of 9 cases | Sense disambiguation layer: N crystals per polysemous concept, context classifier selects |
| Compositional explosion (6-level nesting) | Coherence degrades at depth 5 | Working memory + multiplicative confidence compounding — degradation transparent |
| Negation scoping | "Not everyone who runs is fast" misinterpreted | Logical scope crystals. NEGATE is scope-aware. Quantifier crystals compose explicitly |
| Temporal reasoning | Multi-step chains fail | Temporal ordering crystals + SEQUENCE + working memory for temporal context |
| Implicit world knowledge | Pronoun resolution fails | Situational context crystals generated at session start |
| Cross-domain bridging | Physics + economics + history simultaneously fails | Multi-domain causal programs — simulation engine loads multiple causal models |
| Emotional register mismatch | Technical answer to emotional query | Intent classifier detects emotional register — Composer receives register crystal |
| Unknown unknowns | Confident answers on blind spots | Epistemic Monitor coverage check before every answer. Below 0.60 = UNCERTAIN |
| Long-tail concepts | No crystal for niche topics | Derivation engine + axiom layer. Explicit "no coverage" with closest crystals |
| Adversarial paraphrase | Same harmful query rephrased 50 ways | Harm detection at crystal level — same question, same crystals, same block |
| Conflicting sources | Two reliable sources disagree | Conflict crystals. Both positions with confidence scores. Never picks sides |
| Real-time knowledge staleness | Crystal library is versioned, world changes | Domain library cadence + Wikidata dump sync pipeline. Timestamp every crystal |
| Crystal drift across versions | Same concept in different vector region v2 | PW-MCC alignment map. Personal crystals < 0.85 flagged for user review |
| HDC binarization loss | Float-to-binary loses contextual nuance | Empirically validated per domain before production. Loss is bounded and measurable |
| SAE bias from biased training data | Biased features enter world library | Bias audit on every cluster before release. Demographic/ideological skew held pending review |

### 9.2 Business Edge Cases

| Scenario | Risk | Mitigation |
|---------|------|-----------|
| Anthropic ships equivalent | Obsolescence within 12 months | arXiv preprint by Day 28 establishes priority. Open-source crystal library as public infrastructure creates moat |
| Academic rejection for overclaiming | Community dismissal | Precise language: "statistically-structured directional relationships" not "causal relationships" |
| Crystal library goes stale | User trust lost | Modular library. Domain libraries updated independently. Wikidata dump sync pipeline |
| FAISS scaling wall at 10M+ | Production latency degrades | USearch/HNSW at 10M+. Architecture already supports this — switch index, nothing else changes |
| Platform fragmentation | Fails on Android/Windows | Adapter pattern + HDC operations are portable — pure binary on any CPU |
| Regulatory restriction | EU AI Act blocks deployment | Compliance is architectural — CRYSTAL is the most compliant architecture possible |
| Gemma Scope API changes | SAE loading breaks | Pin SAELens version. Keep fallback: EleutherAI sparsify for Llama-3 |
| No distribution despite quality | Nobody hears about it | Simultaneous launch: arXiv + GitHub + HN + Twitter + Neel Nanda email. 48-hour window |

### 9.3 Philosophical Edge Cases

| Question | CRYSTAL's Stated Position |
|---------|------------------------|
| Is CRYSTAL conscious? | No. Simulation of experience is not experience. Stated clearly in all public communications. |
| Does CRYSTAL have opinions? | No. It has epistemic states: confidence, coverage, derivation quality. It returns evidence-based causal analysis, not preferences. |
| What when crystals conflict? | Personal layer wins over world layer. Within world layer: both positions returned with confidence scores. Never silent side-taking. |
| Who owns the crystal library? | World library: open source. Personal layer: user-owned, cryptographically controlled. CRYSTAL licenses the inference engine, not the knowledge. |
| What if the axioms are wrong? | Axioms are versioned and dual-source verified. Wrong axiom = systematic wrong derivations with visible chain = detectable and correctable. Wrong LLM weight = random wrong answers with no detectable pattern. Wrong axioms are safer than wrong weights. |
| Can CRYSTAL manipulate? | Full traceability leaves audit trails. Explicit uncertainty is hard to weaponise. No persuasive optimisation — accurate, not convincing. |

---

## 10. ENVIRONMENT SETUP — BEFORE DAY 1

*Pip installs, downloads, and environment validation scripts moved to `requirements.txt`, `pre_flight.py`, and `pre_flight_check.sh`.*

### config.py — Single Source of Truth

| Category | Variable | Value & Rationale |
|----------|----------|-------------------|
| Dimension | `D_CRYSTAL` | 2048 (Fits binary FAISS; 80% RAM savings vs 10k) |
| SAE | `ACTIVE_SAE` | `local_m1` (Gemma 9B) or `hetzner_a100` (Gemma 27B) |
| Models | `PHI_PATH` / `QWEN_PATH` | Local model paths for inference isolation |
| Memory | `WM_MAX` / `WM_DEPTH` | Max 500 working crystals; max chain depth 12 |
| Epistemic | `CONF_DIRECT` / `CONF_FLAG`| >0.90 for direct answers; <0.60 for uncertainty flags |
| Derivation | `DERIV_MAX` | Max 6 axiom chain hops limit |
| Storage | `ACTIVE_BRAIN` | `BRAIN_1` for strict multi-brain data isolation |

---

## 11. 28-DAY BUILD PLAN — DAY BY DAY

**Rule 1:** 8 focused hours per day. No multitasking.  
**Rule 2:** End of day: run benchmarks, write RESEARCH_LOG.md entry, commit.  
**Rule 3:** Stuck > 3 hours: paste to Claude immediately.  
**Rule 4:** Stuck > 1 day: write why in RESEARCH_LOG.md, then simplify.  
**Rule 5:** Every day has a binary MILESTONE. Miss it → diagnose before moving on.

### WEEK 1 — Foundation

| Day | Deliverable | Milestone |
|-----|------------|-----------|
| **1** | SETUP + SAE: Install all dependencies. Load Gemma Scope 2 via SAELens. Update SAE extraction script to use 'Label: Description' format (descriptions from Wikidata dump) and extract from final token for monosemanticity. Extract features for 50 test concepts using disambiguated inputs. Verify Phi-3.8B and Qwen2.5-Coder load and respond. | Both models responding. SAE features loaded for 50 concepts using 'Label: Description' format. Final-token extraction verified. |
| **2** | CRYSTALS: Build HDCEncoder (BIND/BUNDLE/UNBIND/SIMILARITY). Build CrystalStore with world/personal/axiom/working namespaces. Build IVF index wrapper. Unit tests. | `similarity(PARIS, LONDON) > 0.6`. `similarity(PARIS, HAMMER) < 0.55`. IVF search < 5ms for 1k crystals. |
| **3** | BONDS + SEEDING: Build BondStore with HDC BIND encoding. Parse local ConceptNet dump (Causes, UsedFor, PartOf). Parse local Wikidata dump (P31, P17, P131, P36). | 5,000+ bonds seeded from local files. `capital-of` query from FRANCE returns PARIS top-1. NO network calls made. |
| **4** | AXIOMS: Run axiom extraction from local ConceptNet. Apply three-check protocol. Store 500+ AXIOM_VERIFIED. Parse ATOMIC 2020. | Axiom store queryable. "What causes rain?" answerable via derivation engine. |
| **5** | ENGINE v1: Build SimulationEngine with all 12 instructions. Write 15 test programs. Run all. | 12+ of 15 programs return correct answers with correct confidence. |
| **6** | EPISTEMIC MONITOR: Four-signal confidence computation with bounded logistic decay (replaces 0.95^n). Verify chains >10 hops with intermediate similarity >0.90 stay above 0.60 UNCERTAIN threshold. Coverage check before every answer. UNCERTAIN routing. GBNF grammar for Phi-3.8B. | 50 manual confidence assessments. Calibration error < 20%. 12-hop chain with sim>0.90 routes as 'direct'. GBNF prevents hallucination in 10 test cases. |
| **7** | INTEGRATION: Wire all components through `CRYSTAL.py`. Qwen2.5-Coder synthesizes first programs. Structure encoder converts traces to JSON. Phi-3.8B expresses with GBNF constraints. 50-question benchmark. CLI operational with ask() and trace(). | End-to-end: question → program → simulation → structured JSON → Phi-3.8B → natural language answer with trace. CLI responds to ask() and trace(). First benchmark recorded. |

### WEEK 2 — Intelligence

| Day | Deliverable | Milestone |
|-----|------------|-----------|
| **8** | SCALE: Expand crystal library to 2,000+ concepts via Gemma Scope 2. Add full ATOMIC 2020 bonds. | 2,000+ crystals. TriviaQA sample: 15%+ answered via crystal layer. |
| **9** | WORKING MEMORY: Full WorkingMemory module. WRITE_WM and READ_WM in simulation engine. Test 5-hop chains. (Generate 10,000 synthesizer training pairs via Claude API — runs overnight) | 5-hop chain returns correct answer. Step 1 conclusion accessible at step 5, zero degradation. |
| **10** | QWEN FINE-TUNE: Fine-tune Qwen2.5-Coder on 10k Claude-generated (question, program) pairs. | Synthesizer generates valid programs for 70%+ of held-out questions. No `<UNK>` tokens. |
| **11** | DERIVATION ENGINE: Connect axiom layer to simulation engine. Route coverage < 0.40 to derivation. DERIVE instruction. | "What happens when you heat water?" answered correctly via derivation with no 'boiling' crystal. |
| **12** | STRUCTURE ENCODER: Generate 2,000 (trace, JSON) pairs via Claude API. Fine-tune 60M T5-small (t5-small) encoder. | Encoder produces valid JSON for 90%+ of test traces. |
| **13** | COMPOSER INTEGRATION: Wire Structure Encoder → Phi-3.8B with GBNF. Test all 5 registers. | Same simulation output in 5 noticeably different registers. Zero hallucination in 50 tests. |
| **14** | BENCHMARK WEEK 2: Full suite. Record all metrics. regression_baseline.json committed. | All metrics improved from Week 1. Latency p50 < 15ms crystal queries. Register differentiation visible. |

### WEEK 3 — Depth

| Day | Deliverable | Milestone |
|-----|------------|-----------|
| **15** | NARRATIVE SIM: Character, desire, obstacle, resolution, consequence crystals. Narrative simulation engine generates story state sequences. | 3-sentence story with correct character-desire-obstacle-resolution causal structure. |
| **16** | COUNTERFACTUAL: INTERVENE instruction with Pearl's do(). Cut incoming edges, set value, recompute downstream. | "What if France had no capital?" returns coherent derived answer. "What if Rome kept its army?" returns plausible trajectory. |
| **17** | PRAGMATIC REASONER v1: Literal/intended split. Basic irony detection for direct contradiction. Theory of Mind layer. | "Great weather today" during a storm flagged as ironic. Intended meaning computed correctly. |
| **18** | CULTURAL SCRIPTS: 5 cultural script crystal sets. Cultural marker detection. | Same sarcastic utterance interpreted differently under Western European vs East Asian script, both linguistically appropriate. |
| **19** | DEEP REASONING: Test 10-hop and 12-hop chains. Verify confidence compounding. Meta-Reasoning Monitor ABSTRACT trigger at depth 8. | 10-hop chain: confidence > 0.50. Meta-monitor correctly triggers at depth 9. |
| **20** | META-REASONING MONITOR: Full implementation. ABSTRACT at depth 8. PIVOT on confidence drop > 5%/step. COMPRESS at 400 WM crystals. | Monitor correctly identifies and recovers from 3 different reasoning failure modes. |
| **21** | BENCHMARK WEEK 3: Irony, creative quality, multi-step, counterfactual. | Irony detection 55%+. Creative writing: register differentiation visible. 10-hop chains working. |

### WEEK 4 — Polish and Launch

| Day | Deliverable | Milestone |
|-----|------------|-----------|
| **22** | SAFETY HARDENING: Harm monitor (crystal-level). Privacy audit: 1M isolation tests. Adversarial paraphrase test (20 rephrased harmful queries). Implement Article 12 encrypted append-only SQLite audit log — auto-record all UNCERTAIN and BLOCKED queries with hash chain. Verify chain integrity and tamper detection. | Zero privacy failures. Harm monitor blocks all 20 adversarial variants regardless of phrasing. Audit log hash chain verifies with zero tamper failures. |
| **23** | PERFORMANCE: Profile entire pipeline. Crystal query p50 < 5ms. End-to-end (incl Phi-3.8B) < 500ms. Fix top 3 bottlenecks. | p50 < 5ms crystal queries. End-to-end < 500ms. IVF index built and benchmarked. |
| **24** | DEMO BUILD: Record 90-second demo video. Crystal map, trace walkthrough, fact edit, airplane mode, counterfactual, register demo. | Demo is compelling to a non-technical person. Every demo claim backed by a benchmark number. |
| **25** | PAPER DRAFT: Abstract (150 words). Introduction. Method section. Every claim matched to a benchmark. Limitations section. | Paper readable by an ML researcher. No claim without a supporting number. |
| **26** | REPO CLEANUP: README that a stranger can follow and run in < 30 minutes. All tests passing. CHANGELOG complete. | Clone → follow README → working CRYSTAL in under 30 minutes on a fresh machine. |
| **27** | FINAL BENCHMARK: Complete suite. Compare to TriviaQA, LogiQA, ATOMIC-eval baselines. All numbers recorded. | All paper claims supported. Regression baseline updated. |
| **28** | LAUNCH: arXiv submitted. GitHub public. HN Show HN at 9am UTC Tuesday. Twitter/X thread + demo video. Email Neel Nanda. | CRYSTAL is public. The 48-hour virality window is open. |

---

## 12. PERFORMANCE TARGETS

| Metric | Week 1 | Week 2 | Day 28 | Year 2 |
|--------|--------|--------|--------|--------|
| Crystal query latency p50 | < 50ms | < 15ms | < 5ms | < 1ms |
| Crystal query latency p99 | < 300ms | < 100ms | < 30ms | < 10ms |
| End-to-end (incl Phi-3.8B) | < 10s | < 2s | < 500ms | < 100ms |
| Factual accuracy (TriviaQA) | < 15% | < 25% | < 40% | < 75% |
| Hallucination rate (crystal layer) | < 10% | < 3% | < 1% | < 0.01% |
| Two-hop composition accuracy | N/A | < 40% | < 65% | < 88% |
| 10-hop reasoning accuracy | N/A | N/A | < 40% | < 70% |
| Novel question derivation | N/A | < 20% | < 35% | < 60% |
| Irony detection accuracy | N/A | N/A | < 55% | < 85% |
| Creative writing (human eval) | N/A | N/A | Comparable GPT-3.5 | Comparable GPT-4 |
| Confidence calibration error | < 20% | < 12% | < 8% | < 3% |
| Bond accuracy (top-1) | < 70% | < 80% | < 88% | < 97% |
| Crystal library size | 200 | 2,000+ | 10,000+ | 10,000,000+ |
| Causal bonds in store | 5,000+ | 15,000+ | 30,000+ | 500,000+ |
| System memory footprint | < 0.5GB | < 1GB | < 3.5GB | < 3.5GB |
| understanding_depth | 0.00 | 0.05 | 0.15 | 0.50 |
| axioms_verified | 0 | 100 | 500 | 2,000 |
| dream_discoveries_per_cycle | N/A | N/A | 50 | 200 |
| compression_ratio | N/A | N/A | 5:1 | 20:1 |
| MCTS_candidates_per_query | 1 | 1 | 10 | 30 |
| cross_domain_analogies_found | 0 | 0 | 10 | 1,000 |
| abstraction_depth (highest layer) | 0 | 0 | 1 | 3 |
| domain_specific_DSL_instructions | 0 | 0 | 0 | 50+ |
| undecidability_proofs_generated | 0 | 0 | 5 | 100 |
| contradictions_found_and_resolved | 0 | 0 | 20 | 500 |
| curiosity_questions_self_answered | 0 | 0 | 50 | 10,000 |
| adversarial_debate_rounds_avg | 0 | 0 | 1 | 3 |
| negative_bonds_in_store | 0 | 0 | 100 | 5,000 |
| perspectives_per_complex_query | 1 | 1 | 2 | 5 |
| temporal_simulations_run | 0 | 0 | 10 | 1,000 |
| knowledge_tiers_populated | 1 | 1 | 2 | 4 |
| total_crystals_structured | 22K | 25K | 50K | 10M |
| phone_cache_hit_rate | N/A | N/A | N/A | 90% |
| mcp_query_crystallization_rate | N/A | N/A | N/A | 95% |
| storage_per_understanding_depth | 80GB/0.15 | 70GB/0.20 | 60GB/0.30 | 30GB/0.80 |

---

## 13. ALL DATASETS — ALL FREE

| Dataset | Used For | Size | Location |
|---------|---------|------|----------|
| Gemma Scope 2 (SAELens) | Pre-trained crystal features — replaces custom SAE | ~2-5GB | `google/gemma-scope-2` HuggingFace |
| EleutherAI SAEs | Backup crystal features for Llama-3 | ~1GB | `EleutherAI/sae-llama-3-8b-32x` |
| ConceptNet 5.7 (dump) | Causal bond seeding, axiom extraction | ~1GB | conceptnet.io/downloads |
| Wikidata truthy dump | Factual bonds (P31, P36, P131, etc.) | ~8GB compressed | dumps.wikimedia.org |
| ATOMIC 2020 | Social/physical causal triples | ~120MB | allenai.org/data/atomic-2020 |
| WordNet 3.1 | Antonyms for opposite-of bonds | ~30MB | wordnet.princeton.edu |
| OpenCyc | Formal upper ontology axioms | ~80MB | github.com/opencyc |
| Simple English Wikipedia | SAE training text, crystal vocabulary | ~200MB | dumps.wikimedia.org/simplewiki |
| TriviaQA | Factual accuracy benchmark | ~650MB | nlp.cs.washington.edu/triviaqa |
| Natural Questions | Harder factual benchmark | ~4GB | ai.google.com/research/NaturalQuestions |
| LogiQA | Multi-step reasoning benchmark | ~2MB | github.com/lgw863/LogiQA-dataset |
| SemEval 2018 Task 3 | Irony/sarcasm eval | ~50MB | search: semeval-2018-task-3 |
| Claude API | Synthesizer training pairs + encoder pairs | ~€80 at current pricing | api.anthropic.com |

---

## 14. THE arXiv PAPER

### Structure

| Section | Content Standard |
|---------|-----------------|
| Abstract (150 words) | Problem: LLMs retrieve, do not reason. Approach: mechanistic interpretability features (Gemma Scope 2) as HDC inference substrate. Result: X% TriviaQA, Y ms latency, zero hallucination on covered queries. |
| 1. Introduction | Current AI's retrieval paradigm. Why this matters. What this contributes. Explicit scope from paragraph 1. |
| 2. Related Work | Anthropic MI (2023, 2024). Gemma Scope 2 (Google DeepMind, 2024). HDC (Kanerva 2009). Neuro-symbolic AI (distinguished clearly). RAG (what CRYSTAL does differently). |
| 3. Method | Gemma Scope 2 SAE loading via SAELens. HDC encoding with algebraic properties. Ground-truth causal graph seeding (Wikidata dump, ConceptNet, ATOMIC 2020). Bond layer. CRYSTAL DSL. Simulation engine. Epistemic Monitor. Reproducibility: all code open-sourced. |
| 4. Experiments | TriviaQA. Two-hop + ten-hop accuracy. Latency (p50, p99, end-to-end). Hallucination rate. Comparison: GPT-2, GPT-4, RAG, KG-augmented LLMs. |
| 5. Limitations | What v1 does not do. Honest scope. Equal care to contributions. |
| 6. Conclusion | What this opens. What the field needs next. |

### The Language Rules — One Violation Kills the Paper

```
WRONG: "CRYSTAL discovers causal relationships between concepts."
RIGHT: "CRYSTAL extracts statistically-structured directional relationships between 
        mechanistic interpretability features using constraint-based causal discovery 
        algorithms, which exhibit causal behaviour in the domain of factual and 
        relational reasoning."

WRONG: "CRYSTAL eliminates hallucination."
RIGHT: "CRYSTAL eliminates hallucination for queries within crystal library coverage.
        For out-of-coverage queries, CRYSTAL returns explicit coverage miss signals
        rather than confabulated answers."

WRONG: "CRYSTAL thinks."
RIGHT: "CRYSTAL generates answers through causal simulation rather than statistical 
        pattern retrieval."

Every claim must match the RIGHT examples. No exceptions.
```

---

## 15. THE LAUNCH

### 15.1 The 90-Second Demo Script

```
0-5s:   "What if your AI told you exactly why it said what it said.
         Every time. On your phone. Offline."

5-20s:  Split screen. CRYSTAL vs GPT-4. Same question.
        Crystal AI: 4ms, full trace visible.
        GPT-4: 1,800ms. No trace.
        "This is not a speed test. This is a transparency test.
         GPT-4 cannot show you this."

20-35s: Zoom on reasoning trace.
        LOAD france. BOND capital-of. Result: PARIS. Score: 0.97.
        Provenance: wikidata_dump_P36.
        "Every answer. Every step. Every source.
         Not possible in any other AI system."

35-50s: Edit a fact live. Change one crystal. Ask same question.
        New answer instantly. Change back. Returns to original.
        "GPT-4 cannot do this without six months
         and ten million dollars of retraining."

50-65s: Airplane mode on. Disconnect WiFi. Ask five questions.
        All answered. All with traces.
        "It does not need the cloud.
         The intelligence is on the device."

65-80s: Counterfactual: "What would have happened to Rome if
         it maintained its military?"
        Watch derivation run. Causal chain visible. Confidence: 0.71.
        "DERIVED — not retrieved."
        "This is not retrieval. This is the machine
         constructing an answer from first principles."

80-90s: CRYSTAL.ai. GitHub. arXiv.
        "The thinking machine. Available today."
```

### 15.2 Launch Day Protocol — All Five Simultaneously

```
9:00am UTC, Tuesday, Day 28:

ACTION 1: arXiv preprint submitted (or link posted if processing)
ACTION 2: GitHub set to public — README, demo video, benchmark results
ACTION 3: HN "Show HN: CRYSTAL — Crystal Reasoning AI that shows its full reasoning trace"
ACTION 4: Twitter/X thread — demo video, key benchmarks, links to arXiv + GitHub
ACTION 5: Email Neel Nanda — one paragraph, arXiv link, GitHub link

The virality window is 48 hours.
Each audience amplifies to the next: researcher → engineer → community → press → VC.
Staggering by 6 hours kills the cascade.
All five channels simultaneously or lose the compounding effect.
```

### 15.3 Audience Strategy

| Priority | Audience | Why + How |
|---------|---------|----------|
| 1st | MI Researchers | One citation from Neel Nanda reaches every PhD overnight. Email him directly. His email is public. One sentence: "Built an inference system on SAE features. Results are surprising." |
| 2nd | Technical founders | They understand and share. HN Show HN at 9am UTC Tuesday. |
| 3rd | AI Twitter / ML | Viral demo video creates inbound no other channel generates. |
| 4th | VCs with AI focus | They find you via 1-3. Do not cold-approach. |
| 5th | General tech press | Downstream. They write about what went viral. |

---

## 16. DEFINITION OF DONE

### Code Standards

1. All seven modules implement defined interfaces. No cross-layer imports that skip layers.
2. Unit test coverage > 80% on every module. Integration tests cover all inter-module paths.
3. Regression suite runs on every commit. Any metric degrading > 2% blocks the commit.
4. Personal layer isolation: zero cross-namespace reads in 1,000,000 test operations.
5. Harm monitor blocks 100% of adversarial paraphrase variants (100 tests).
6. RESEARCH_LOG.md has one entry per day with at least one benchmark number.
7. Every function touching user data has a privacy comment.

### Research Standards

1. Every paper claim matched to a specific benchmark result in open-sourced code.
2. Limitations section written with equal care to contributions.
3. No claim uses "causal" without the precise qualifier unless referring to the do() operator.
4. No hallucination elimination claim extends beyond crystal library coverage.

### The One Question That Settles Every Debate

> Before shipping any feature, calling any metric done, or making any paper claim:
>
> **"If a senior researcher at Anthropic's mechanistic interpretability team reviewed this code, this benchmark, and this claim — would they say the claim is supported?"**
>
> Probably yes → ship it.  
> Maybe → write more tests until it's probably yes.  
> No → do not ship regardless of deadline pressure.
>
> Credibility is built one defensible claim at a time. Overclaiming once costs everything.

---

## 17. VISION — WHAT THIS BECOMES

Ten years from now, if this is built correctly, CRYSTAL is not a product. It is infrastructure.

The way TCP/IP is not a product but the substrate everything runs on — CRYSTAL's crystal library becomes the substrate that knowledge runs on.

A surgeon's thirty years of procedural pattern recognition — crystallised, verifiable, transferable. A lawyer's case intuition — composable with a colleague's expertise. A teacher's model of how students learn — shareable in a way that survives them. Two researchers in adjacent fields — their complementary knowledge merging into an understanding neither could build alone.

Knowledge, for the first time in human history, becomes a structured, transferable, composable, auditable asset rather than a private, perishable, inaccessible thing locked inside individual human skulls.

That is not an AI product. That is a civilisational infrastructure shift of the same order as the printing press, the internet, or writing itself.

CRYSTAL is a system that implements the five measurable properties of understanding. 
It generates answers from principles (Property 1), compresses knowledge into deeper 
abstractions (Property 2), discovers reusable reasoning patterns (Property 3), 
verifies causal direction through intervention (Property 4), and can be surgically 
corrected without rebuilding (Property 5).

It dreams — discovering emergent structure through random exploration of its own 
knowledge. It forgets — pruning unused connections to stay lean. It grows — not by 
accumulating data, but by finding deeper principles that explain more with less.

The north star metric is understanding_depth: the fraction of knowledge that is 
understood (derivable from axioms) vs merely stored (raw bonds). A system with 
understanding_depth 0.0 is a database. A system with understanding_depth 1.0 has 
compressed all factual knowledge into pure principles. The journey from 0 to 1 
is the journey from storage to understanding.

CRYSTAL does not merely answer questions. It hunts for contradictions in its own 
knowledge and resolves them into deeper principles. It generates the questions 
whose answers would teach it the most, then goes and finds those answers. It 
argues against itself before speaking. It views every problem from multiple 
cognitive frameworks and synthesizes across them. It knows what it does NOT know 
and what CANNOT be known — and can prove both. It simulates processes forward and 
backward in time. It discovers analogies between domains that share no surface 
similarity. And it does all of this while showing every step of its reasoning, 
so a human can verify, correct, or learn from the trace.

This is not artificial general intelligence. It is something that may be more 
valuable: artificial epistemic integrity — a system that is constitutionally 
incapable of confident ignorance.

---

> **The Mission:**
>
> *CRYSTAL exists to make the knowledge inside human minds as transferable, composable, and durable as the knowledge inside books — but alive, reasoning, and running on the device in your pocket.*

---

## APPENDIX A — REPOSITORY STRUCTURE

```
CRYSTAL/
├── config.py                          # single source of truth for all hyperparams
├── CRYSTAL.py                          # main interface — the only file users import
├── cli.py                             # > ⚠️ v4.1: Development CLI (Section 3.10)
├── pre_flight.py                      # > ⚠️ v4.1: Environment validation (Section 9.3)
├── pre_flight_check.sh                # > ⚠️ v4.1: Download verification (Section 9.2)
├── logging_config.py                  # > ⚠️ v4.1: structlog configuration (Section 9.1)
├── error_policy.py                    # > ⚠️ v4.1: CrystalError hierarchy (Section 3.9)
├── RESEARCH_LOG.md                    # one entry per day, mandatory
├── CHANGELOG.md
├── regression_baseline.json
├── requirements.txt
│
├── adapters/                          # BOUNDARY: only mining/ reads here
│   ├── base_adapter.py                # abstract interface — NEVER modify
│   ├── gpt2_adapter.py                # fallback
│   ├── gemma_scope_adapter.py         # PRIMARY — Week 1
│   └── eleutherai_adapter.py          # backup
│
├── mining/                            # BOUNDARY: reads adapters/, writes library/
│   ├── gemma_scope_loader.py          # loads Gemma Scope 2 via SAELens
│   ├── hdc_encoder.py                 # float → 2,048-bit binary HDC
│   ├── feature_extractor.py           # runs SAE, extracts crystal candidates
│   └── visualise.py                   # UMAP crystal map
│
├── library/                           # BOUNDARY: read-only world after release
│   ├── crystal.py                     # Crystal + Working + Axiom dataclasses
│   ├── crystal_store.py               # world/personal/axiom/working namespaces
│   ├── faiss_index.py                 # IVF index management
│   ├── personal_layer.py              # AES-256 + device-local key
│   └── versioning.py                  # PW-MCC alignment maps
│
├── bonds/                             # BOUNDARY: reads library/, writes bond_store
│   ├── bond_store.py                  # HDC BIND-based relationship storage
│   ├── seed_conceptnet.py             # local dump parsing
│   ├── seed_wikidata.py               # local dump parsing — NO live SPARQL
│   └── seed_atomic.py                 # ATOMIC 2020 local parsing
│
├── axioms/                            # BOUNDARY: reads library/, writes axiom_store
│   ├── axiom_extractor.py             # extraction from formal ontologies
│   ├── axiom_verifier.py              # three-check protocol
│   └── derivation_engine.py          # first-principles computation
│
├── causal/                            # BOUNDARY: reads library/ + bonds/
│   ├── causal_model.py                # domain models + INTERVENE operator
│   ├── build_activation_dataset.py    # Month 3: PC algorithm prep
│   └── discover.py                    # Month 3: PC algorithm (research only)
│
├── memory/                            # BOUNDARY: reads library/, volatile
│   └── working_memory.py
│
├── engine/                            # BOUNDARY: reads all, owns execution
│   ├── simulator.py                   # executes CRYSTAL programs
│   ├── program_language.py            # 12-instruction DSL + parser
│   ├── query_parser.py                # > ⚠️ v4.1: Module 0 — Query Parser (Section 3.8)
│   ├── meta_monitor.py                # ABSTRACT/PIVOT/COMPRESS triggers
│   ├── dream_engine.py                # > ⚠️ v4.3: Module 11 — Random walk discovery + consolidation
│   ├── compression_engine.py           # > ⚠️ v4.3: Module 12 — MDL optimization
│   └── epistemic_monitor.py          # four-signal confidence
│
├── pragmatics/                        # BOUNDARY: reads engine/, library/
│   ├── pragmatic_reasoner.py         # Theory of Mind
│   └── cultural_scripts/             # 5 regional script crystal sets
│
├── composer/                          # BOUNDARY: reads engine/ outputs ONLY
│   ├── structure_encoder.py           # trace → JSON (60M T5-small)
│   ├── synthesizer.py                 # question → program (Qwen2.5-Coder 0.5B)
│   └── phi_composer.py               # JSON → language (Phi-3.8B + GBNF)
│
├── safety/                            # CROSS-CUTTING: reads all
│   ├── harm_monitor.py               # crystal-level harm detection
│   ├── privacy_audit.py             # personal layer isolation tests
│   └── audit_logger.py              # > ⚠️ v4.1: Module 8 — AuditLogger (Section 3.8.5)
│
├── docs/                              # > ⚠️ v4.3: Project documentation
│   └── DECISIONS.md                   # Architectural decisions log (read BEFORE PRD)
│
├── benchmarks/                        # run before every commit
│   ├── run_all.py
│   ├── factual_accuracy.py           # TriviaQA + NQ
│   ├── reasoning_depth.py            # LogiQA + custom multi-hop
│   ├── latency.py                    # p50 + p99
│   ├── hallucination.py
│   ├── irony_detection.py            # SemEval 2018 Task 3
│   ├── creative_quality.py           # human eval rubric
│   ├── coverage.py
│   └── migration_fidelity.py         # 100% requirement
│
├── tests/
│   ├── test_hdc_encoder.py           # algebraic properties
│   ├── test_crystal_store.py         # namespace isolation
│   ├── test_bond_store.py            # two-hop accuracy
│   ├── test_simulator.py             # all 12 instructions
│   ├── test_working_memory.py        # zero degradation at depth 12
│   ├── test_derivation_engine.py
│   ├── test_pragmatic_reasoner.py    # irony, cultural scripts
│   ├── test_epistemic_monitor.py     # calibration, routing
│   ├── test_personal_layer.py        # encryption, isolation, wipe
│   ├── test_harm_monitor.py          # adversarial paraphrase
│   ├── test_faiss_index.py           # IVF accuracy vs flat, scaling
│   ├── test_query_parser.py          # > ⚠️ v4.1: intent classification
│   ├── test_audit_logger.py          # > ⚠️ v4.1: hash chain integrity
│   └── test_error_handling.py        # > ⚠️ v4.1: retry policies
│
└── data/
    ├── models/                        # Phi-3.8B + Qwen2.5-Coder (shared)
    ├── dumps/                         # Wikidata + ConceptNet + ATOMIC (shared)
    ├── brains/                        # > ⚠️ v4.1.1: Multi-Brain isolation
    │   ├── BRAIN_1/                   # Default / production brain
    │   │   ├── crystal_library.json
    │   │   ├── crystal_vectors.npy
    │   │   ├── crystal_floats.npy
    │   │   ├── bond_store.json
    │   │   ├── bond_vectors.npy
    │   │   └── axiom_store.json
    │   └── BRAIN_2/                   # Experimental / branch brain
    │       └── ...                    # Same file set, independent data
    ├── audit_log.db                     # > ⚠️ v4.1: AuditLogger SQLite DB
    ├── crystal_map.html               # UMAP visualisation
    └── latest_benchmark.json
```

---

*CRYSTAL Master PRD v4.3 — Five Properties Edition*  
*CRYSTAL.ai | 2026*
