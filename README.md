## Dimitry Donaire — Applied AI Engineer

I build AI systems that run in production and carry their own measurements: retrieval pipelines with evaluation harnesses, multi-tenant LLM infrastructure, and computer vision on edge hardware.

**Python · PostgreSQL/pgvector · TypeScript · Docker · LLMOps** — Ovalle, Chile.
Open to remote roles; hybrid or on-site for the right offer.

📧 dimitrydonaire@gmail.com · [LinkedIn](https://linkedin.com/in/dimitry-donaire-6828aa400)

> **NUMEN AI is my own product, in operation.** I'm looking for a full-time engineering role where I can apply what I learned building and running it.

---

### How I work

Systems get instrumented before they get optimised. Most of what I've written publicly is about measurement going wrong — a hybrid search that silently regressed to pure vector similarity, a cleanup with zero effect on the golden set and 100%→0% effect in production, an evaluation judge that fabricated a convincing finding by reading truncated input.

**That last one I retracted.** The judge was truncating its own input, penalising exactly the long answers that vague questions produce. I measured the judge's own noise floor (~9 pts) by repeat-judging identical inputs, then used it to withdraw a finding I had already published. Negative results are documented alongside the wins.

Before AI I spent **8+ years in safety-critical industrial environments** — mining, power generation, industrial construction (2016–2025). That's where the reflex comes from: circuit breakers, dead-letter queues, spend caps and auto-resume aren't patterns I read about, they're the shape of how you work when a failure is expensive and nobody is coming to help.

---

### What I'm working on

**[NUMEN AI](https://numen-ai.cl)** — multi-tenant conversational AI platform, in production
[Architecture docs →](https://github.com/lindermannn/numen-platform)

Five live channels (WhatsApp including voice notes, Telegram, Instagram DM, Messenger, web chat) over ~70 modular n8n workflows. Hybrid RAG per tenant, PostgreSQL RLS, JWT-derived tenancy, per-tenant spend caps that cut before the bill surprises anyone, and a real-time dashboard for live operator takeover at zero token cost.

`Cut idle executions by 90% — 9,330 → 936/month, with no loss of capability.`

**[huberman-rag-eval](https://github.com/lindermannn/huberman-rag-eval)** — production RAG with a measured evaluation harness
[Live demo →](https://production-hybrid-rag.lovable.app)

27,254 chunks from ~417 podcast episodes. Hybrid retrieval (pgvector + Postgres full-text, fused with RRF), LLM query rewriting, LLM rerank.

| Recall@8 | MRR | Context relevance | Groundedness | Judge noise floor |
|---|---|---|---|---|
| 78.1% | 0.593 | 83.8% | 93.2% | ~9 pts |

The metric code is covered by tests that run in CI — including one that pins the exclusion rule behind the recall denominator, so the number can't quietly change meaning.

**[edge-ai-surveillance](https://github.com/lindermannn/edge-ai-surveillance)** — embedded computer vision for public tenders
*Architecture public, implementation private.*

**Current:** validated multi-camera prototype on x86/Windows against live RTSP streams — Go2RTC, OpenCV, tenant-isolated Supabase backend, 317 tests, CI.
**Target:** RK3576/NPU appliance using YOLO compiled to RKNN, ByteTrack, <200 ms glass-to-glass, 4 concurrent streams at 15+ FPS.

Events cross the network; video does not.

---

`Python` · `TypeScript` · `JavaScript / Node` · `PostgreSQL / pgvector` · `Supabase` · `Docker` · `FastAPI` · `Next.js` · `LangGraph` · `OpenAI API` · `MediaPipe` · `YOLO / RKNN` · `FFmpeg` · `n8n`
