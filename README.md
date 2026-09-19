### Hi, I'm Oleg

Senior backend engineer building production AI systems — not demos, not notebooks, not "I wrapped GPT."

I build tool-first orchestration layers where the language model is the mouth, not the decision-maker. Every project below ships with tests, CI, and honest documentation about what works and what doesn't.

---

### Stack

**Backend**: Python 3.12, FastAPI, Pydantic, PyTorch, scikit-learn, NumPy, pandas
**Retrieval**: pgvector, FAISS, BM25 + dense hybrid, reciprocal rank fusion
**Infra**: Docker, Kubernetes, GitHub Actions, PostgreSQL, SQLite
**Frontend**: TypeScript, React, Next.js, Vercel AI SDK
**Voice**: SSE/WebSocket streaming, STT/TTS pipelines

---

### Featured Projects

#### [Voice Agent Orchestration (Helix)](https://github.com/OlegUnreal/voice-agent-orchestration)
Tool-first supervisor over MCP tools. Python owns the numbers — the model never picks tools and never invents prices. Hybrid retrieval (BM25 + dense + RRF), multi-tier reranking (RankNet → CrossEncoder → fine-tuned BERT on RTX 2060), SSE/WebSocket streaming, model drift detection, A/B testing, performance dashboard, EvalForge golden set with promotion gates. Docker + Kubernetes + TorchServe. **50 tests passing.**

*This is the Python engine + voice UI. The TypeScript frontend is a separate repo below.*

#### [Multi-Agent Debate](https://github.com/OlegUnreal/multi-agent-debate)
Three LLMs with isolated memory argue positions, rank arguments with Bradley-Terry MLE, and reach consensus via a judge rubric with calibration (ECE). Live web UI streams every round in real time. Memory retrieval: TF-IDF + SVD embeddings, IVF index, MMR diversity, token-budget packing. Cross-debate episodic memory in SQLite. **84 tests passing.**

#### [Self-Healing Pipeline](https://github.com/OlegUnreal/self-healing-pipeline)
An agent that runs a failing test, reads the traceback, and repairs the workspace until the suite is green. Three repair modes: diff loop, tool loop, LangGraph graph loop. Subprocess sandbox with `RLIMIT_AS`, workspace jail, failure classifier (scikit-learn), semantic repair memory. Not retry — learns from past failures. **153 tests passing.**

#### [Synthetic Data Factory](https://github.com/OlegUnreal/synthetic-data-factory)
Turns 5–20 seed examples into a quality-filtered training dataset. Six-module AI stack: order-sensitive shingles, 4-backend embeddings (hashing / TF-IDF+LSA / OpenAI / sentence-transformers), MinHash+LSH + IVF ANN dedup with exact cosine verification, independent judge filter, leakage-audited stratified splits, reproducibility manifest. **28 tests passing.**

#### [Agentic Browser](https://github.com/OlegUnreal/agentic-browser)
LLM agent that drives a real browser via Playwright. Semantic element retrieval (hashed n-grams + MMR), learned selector ranker (19-feature logistic regression, MRR 0.98 vs 0.94 heuristic), episodic memory (SQLite), feedback loop from click outcomes. Safety: domain allow-list + rate limit. **17 tests passing.**

#### [Voice Agent Orchestrator](https://github.com/OlegUnreal/voice-agent-orchestrator)
Production-style voice agent backend in Python. Hybrid retrieval (BM25 + dense TF-IDF/SVD + RRF), learned reranker (7-feature logistic regression, Platt-calibrated), evidence gate, PII redaction, injection defenses, golden eval harness (50 queries, MRR 0.96, nDCG@10 0.83). Offline mode for CI. **27 tests passing.**

*This is the standalone Python backend. The TypeScript voice UI for Helix is in the voice-agent-orchestration repo.*

---

### Core AI/ML Infrastructure

Production-grade infrastructure components for ML systems. Each is a standalone service with FastAPI, Pydantic v2, pytest, Docker, and Hatch build system.

#### [RetrievalForge](https://github.com/OlegUnreal/retrievalforge) — Advanced RAG Pipeline
Hybrid search with 5 chunking strategies (fixed_size, sentence, paragraph, recursive, semantic), BM25 sparse + dense cosine similarity search, 3 reranking algorithms (RRF, MMR, weighted score). Multi-index management with per-index configuration. **62 tests passing.**

#### [AgentForge](https://github.com/OlegUnreal/agentforge) — Autonomous Agent Framework
Think-plan-act-observe loop with multi-step plan execution. Tool registry with parameter validation and handler support. Importance-weighted semantic memory with LRU eviction. Agent orchestrator with status tracking. **68 tests passing.**

#### [LabelForge](https://github.com/OlegUnreal/labelforge) — Data Labeling Platform
Hierarchical label schemas, multi-annotator annotations, review workflows. Inter-annotator agreement scoring (pairwise agreement + majority label). Task queue with lifecycle management (draft→active→paused→completed→archived), overdue detection. **80 tests passing.**

#### [DataWeave](https://github.com/OlegUnreal/dataweave) — Feature Store for ML
Feature definitions with entity-based value storage, feature groups, statistics. Transform engine with 7 types (normalize, standardize, one_hot, label_encode, log, bin, fill_na) using fit/apply pattern. Feature serving API. **70 tests passing.**

#### [ModelMesh](https://github.com/OlegUnreal/modelmesh) — Model Registry & Serving
Model versioning with metadata, stage transitions (development→staging→production→archived). Model comparison with metric tracking. Serving endpoints with load balancing simulation. **60 tests passing.**

#### [TraceMind](https://github.com/OlegUnreal/tracemind) — LLM Observability & Tracing
Distributed tracing for LLM calls with span hierarchy. Performance metrics (latency, token usage, cost). Error tracking with exception spans. Trace search and filtering. **55 tests passing.**

#### [StreamForge](https://github.com/OlegUnreal/streamforge) — Real-time Data Processing
Event-driven pipeline with pub/sub messaging. Windowing strategies (tumbling, sliding, session). Watermark-based late data handling. Exactly-once processing semantics. **66 tests passing.**

#### [EvalBench](https://github.com/OlegUnreal/evalbench) — LLM Evaluation Benchmark
Evaluation datasets with versioning. Multiple metrics (BLEU, ROUGE, BERTScore, perplexity). Leaderboard with statistical significance testing. Regression detection with baseline comparison. **44 tests passing.**

#### [CacheFlow](https://github.com/OlegUnreal/cacheflow) — Semantic LLM Response Cache
Semantic similarity cache using embeddings. Cache invalidation strategies (TTL, LRU, LFU). Hit rate monitoring and metrics. Batch cache warming. **51 tests passing.**

#### [GuardRail](https://github.com/OlegUnreal/guardrail) — AI Safety & Guardrails
Input/output validation with regex + semantic rules. PII detection and redaction. Toxicity scoring with threshold enforcement. Prompt injection detection. **65 tests passing.**

#### [PromptLab](https://github.com/OlegUnreal/promptlab) — Prompt Engineering Platform
Prompt versioning with A/B testing. Template engine with variable substitution. Execution tracking with token usage. Prompt performance comparison. **64 tests passing.**

#### [VectorForge](https://github.com/OlegUnreal/vectorforge) — Vector Similarity Search
Multiple index types (flat, IVF, HNSW). Distance metrics (cosine, L2, dot product). Batch search with result deduplication. Index statistics and monitoring. **58 tests passing.**

#### [GraphMind](https://github.com/OlegUnreal/graphmind) — Knowledge Graph RAG
Entity extraction and relationship mapping. Graph-based retrieval with neighborhood expansion. Path-based reasoning. Hybrid graph + vector search. **52 tests passing.**

#### [DocuMind](https://github.com/OlegUnreal/documind) — Document Intelligence Pipeline
Document parsing (PDF, DOCX, HTML). Layout analysis with section detection. Table extraction with structure preservation. Multi-modal document understanding. **47 tests passing.**

#### [Nexus](https://github.com/OlegUnreal/nexus) — LLM Inference Gateway
Multi-provider routing (OpenAI, Anthropic, local models). Load balancing with circuit breaker. Request/response transformation. Token usage tracking and rate limiting. **53 tests passing.**

---

### How the pieces fit

```
voice-agent-orchestration (Helix)
├── python/helix/     ← Python engine: tools, quant, RAG, reranking, evals
├── src/              ← TypeScript voice UI + fallback router
└── k8s/              ← Kubernetes manifests

voice-agent-orchestrator
└── src/voice_agent/  ← Standalone Python backend: retrieval, safety, evals

multi-agent-debate    ← Adversarial consensus with Bradley-Terry ranking
self-healing-pipeline ← Auto-repair agent with sandbox + learned failure classes
synthetic-data-factory ← Quality-gated synthetic data with ANN dedup
agentic-browser       ← Browser automation with semantic retrieval + learned ranking

Core AI/ML Infrastructure:
┌─────────────────────────────────────────────────────────────┐
│  Retrieval & Search                                          │
│  ├── RetrievalForge (RAG pipeline + chunking + reranking)   │
│  ├── VectorForge (vector similarity search)                 │
│  ├── GraphMind (knowledge graph RAG)                        │
│  └── CacheFlow (semantic cache)                             │
├─────────────────────────────────────────────────────────────┤
│  Agent & Orchestration                                       │
│  ├── AgentForge (autonomous agents)                         │
│  ├── Nexus (LLM gateway)                                    │
│  └── ModelMesh (model registry + serving)                   │
├─────────────────────────────────────────────────────────────┤
│  Data & ML Ops                                               │
│  ├── DataWeave (feature store)                              │
│  ├── LabelForge (data labeling)                             │
│  ├── DocuMind (document intelligence)                       │
│  └── StreamForge (real-time processing)                     │
├─────────────────────────────────────────────────────────────┤
│  Quality & Safety                                            │
│  ├── GuardRail (safety & guardrails)                        │
│  ├── EvalBench (evaluation benchmark)                       │
│  ├── TraceMind (observability & tracing)                    │
│  └── PromptLab (prompt engineering)                         │
└─────────────────────────────────────────────────────────────┘
```

---

### What every project has

- Tests that run offline (no API key needed for CI)
- Honest "what works / what doesn't" documentation
- Design decisions written for interview defense
- Architecture diagrams
- Configuration via env / .env (secrets never in source)
- FastAPI + Pydantic v2 + pytest + Docker + Hatch

---

*Last updated: 2026-09-19*
