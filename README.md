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

### How the pieces fit

```
voice-agent-orchestration (Helix)
├── python/helix/     ← Python engine: tools, quant, RAG, reranking, evals
├── src/              ← TypeScript voice UI + fallback router
└── k8s/              ← Kubernetes manifests

voice-agent-orchestrator
└── src/voice_agent/  ← Standalone Python backend: retrieval, safety, evals
                        (proves the retrieval + safety pattern independently)

multi-agent-debate    ← Adversarial consensus with Bradley-Terry ranking
self-healing-pipeline ← Auto-repair agent with sandbox + learned failure classes
synthetic-data-factory ← Quality-gated synthetic data with ANN dedup
agentic-browser       ← Browser automation with semantic retrieval + learned ranking
```

---

### What every project has

- Tests that run offline (no API key needed for CI)
- Honest "what works / what doesn't" documentation
- Design decisions written for interview defense
- Architecture diagrams
- Configuration via env / .env (secrets never in source)

---

*Last updated: 2026-09-19*
