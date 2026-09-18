### Hi, I'm Oleg

Senior backend engineer building production AI systems — not demos, not notebooks, not "I wrapped GPT."

I build tool-first orchestration layers where the language model is the mouth, not the decision-maker. Every project below ships with tests, CI, Docker, and honest documentation about what works and what doesn't.

---

### Stack

**Backend**: Python 3.12, FastAPI, Pydantic, PyTorch, scikit-learn, NumPy, pandas
**Retrieval**: pgvector, FAISS, BM25 + dense hybrid, reciprocal rank fusion
**Infra**: Docker, Kubernetes, GitHub Actions, PostgreSQL, SQLite
**Frontend**: TypeScript, React, Next.js, Vercel AI SDK
**Voice**: SSE/WebSocket streaming, STT/TTS pipelines

---

### Featured Projects

#### [Voice Agent Orchestration](https://github.com/OlegUnreal/voice-agent-orchestration)
Tool-first supervisor over MCP tools. Hybrid retrieval (BM25 + dense + RRF), multi-tier reranking (RankNet → CrossEncoder → fine-tuned BERT), streaming for voice UIs, model drift detection, A/B testing, performance dashboard, EvalForge golden set with promotion gates. Fine-tuned DistilBERT reranker on RTX 2060. 50 tests passing.

#### [Multi-Agent Debate](https://github.com/OlegUnreal/multi-agent-debate)
Agents retrieve from shared memory, argue positions, rank arguments with Bradley-Terry scores. Structured debate protocol with evidence citation and concession tracking. Live web UI to watch agents reach consensus.

#### [Self-Healing Pipeline](https://github.com/OlegUnreal/self-healing-pipeline)
ML pipeline that detects failures, diagnoses root causes, applies semantic repair memory. Trained failure classifier (scikit-learn), LangGraph orchestration with checkpointing. Not retry — learns from past failures.

#### [Synthetic Data Factory](https://github.com/OlegUnreal/synthetic-data-factory)
Generate synthetic datasets with real embeddings (sentence-transformers), ANN deduplication (FAISS), quality metrics (KS test, correlation preservation), privacy metrics (distance to nearest neighbor). Leakage-audited train/val/test splits.

#### [Agentic Browser](https://github.com/OlegUnreal/agentic-browser)
Browser automation agent that retrieves elements by semantic meaning, not CSS selectors. Learns action sequences from demonstrations. Playwright/Chromium with safety policy and visual debugging.

#### [Voice Agent Orchestrator](https://github.com/OlegUnreal/voice-agent-orchestrator)
TypeScript voice UI for the Python engine. STT → engine → TTS. Fallback intent router if Python gateway is down. React components for voice interaction, markets, RAG, evals, training.

---
