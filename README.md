## Dimitry Donaire — Applied AI Engineer

I build AI systems that run in production and carry their own measurements: retrieval pipelines with evaluation harnesses, multi-tenant LLM infrastructure, and computer vision on edge hardware.

**Python · PostgreSQL/pgvector · TypeScript · Docker · LLMOps** — Ovalle, Chile.
Open to remote roles; hybrid or on-site for the right offer.

📧 dimitrydonaire@gmail.com · [LinkedIn](https://linkedin.com/in/dimitry-donaire-6828aa400)

---

### Background

8+ years in safety-critical industrial environments — mining, power generation, industrial construction (2016–2025) — before moving into AI. Circuit breakers, dead-letter queues, spend caps and auto-resume are not patterns I read about; they're how you build when failure is expensive and no one is coming to help.

Most of what I publish is about measurement going wrong: a hybrid search that silently regressed to pure vector similarity, a cleanup with zero effect on the golden set and full effect in production, an evaluation judge that fabricated a finding by reading truncated input. That last one I retracted — I measured the judge's own noise floor (~9 pts) and used it to withdraw a result I had already published. Negative results are documented alongside the wins.

---

### Projects

**[NUMEN AI](https://numen-ai.cl)** — multi-tenant conversational AI platform, in production. [Architecture →](https://github.com/lindermannn/numen-platform)

Five channels (WhatsApp including voice notes, Telegram, Instagram DM, Messenger, web chat) over ~70 modular n8n workflows. Hybrid RAG per tenant, PostgreSQL RLS, JWT-derived tenancy, per-tenant spend caps, real-time dashboard for operator takeover at zero token cost. Idle executions cut 90% — 9,330 → 936/month — with no loss of capability.

**[huberman-rag-eval](https://github.com/lindermannn/huberman-rag-eval)** — production RAG with a measured evaluation harness. [Live demo →](https://production-hybrid-rag.lovable.app)

27,254 chunks from ~417 podcast episodes. Hybrid retrieval (pgvector + Postgres full-text, fused with RRF), LLM query rewriting, LLM rerank.

| Recall@8 | MRR | Context relevance | Groundedness | Judge noise floor |
|---|---|---|---|---|
| 78.1% | 0.593 | 83.8% | 93.2% | ~9 pts |

Metric code is covered by CI tests, including one that pins the exclusion rule behind the recall denominator so the number can't quietly change meaning.

**[edge-ai-surveillance](https://github.com/lindermannn/edge-ai-surveillance)** — embedded computer vision for public tenders. Architecture public, implementation private.

**Validated:** multi-camera prototype on x86/Windows against live RTSP streams — Go2RTC, OpenCV, tenant-isolated Supabase backend, 317 tests, CI.
**Targeted, not yet measured:** RK3576/NPU appliance, YOLO compiled to RKNN, ByteTrack, <200 ms glass-to-glass, 4 concurrent streams at 15+ FPS — the benchmark harness is built and gated in CI; the 24-hour validation campaign on-device hasn't run yet.

Events cross the network; video does not.

---

`Python` · `TypeScript` · `JavaScript / Node` · `PostgreSQL / pgvector` · `Supabase` · `Docker` · `FastAPI` · `Next.js` · `LangGraph` · `OpenAI API` · `MediaPipe` · `YOLO / RKNN` · `FFmpeg` · `n8n`
