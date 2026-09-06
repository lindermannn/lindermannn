## Dimitry Donaire — Applied AI Engineer

I build AI systems that run in production and carry their own measurements: retrieval pipelines with evaluation harnesses, multi-tenant LLM infrastructure, and computer vision on edge hardware.

Based in Chile. Currently building [NUMEN AI](https://numen-ai.cl).

---

### What I'm working on

**[NUMEN AI](https://numen-ai.cl)** — multi-tenant conversational AI platform, in production
Six channels (WhatsApp, Telegram, Instagram, Messenger, email, web), hybrid RAG, per-tenant spend caps, PostgreSQL RLS, and a human-in-the-loop dashboard for live operator takeover. Cut idle executions by 90% (9,330 → 936/month) without losing capability.

**[huberman-rag-eval](https://github.com/lindermannn/huberman-rag-eval)** — production RAG with a measured evaluation harness
27,254 chunks from ~417 podcast episodes. Recall@8 78.1% · groundedness 93.2% · judge noise floor ~9 pts. The harness caught its own measurement bias and forced an earlier finding to be retracted — that write-up is the most useful thing in the repo.

**[gym-hype-video-pipeline](https://github.com/lindermannn/gym-hype-video-pipeline)** — agentic multimodal video processing
MediaPipe pose → LangGraph planning → deterministic FFmpeg render, 568 tests, effects verified against real frames. Design rule that came out of it: a signal component is dropped when its landmarks aren't visible, rather than tuning a threshold per exercise.

**Edge AI surveillance** *(private, in progress)* — YOLO → RKNN on an RK3576 NPU, ByteTrack, Go2RTC/WebRTC, Supabase backend. Targets: <200 ms glass-to-glass, 4 concurrent streams at 15+ FPS.

---

### How I work

Systems get instrumented before they get optimised. Most of what I've written publicly is about measurement going wrong — a hybrid search that silently regressed to pure vector similarity, a cleanup with zero effect on the golden set and 100%→0% effect in production, an evaluation judge that fabricated a convincing finding by reading truncated input. Negative results are documented alongside the wins.

---

`Python` · `JavaScript / Node` · `TypeScript` · `PostgreSQL / pgvector` · `Supabase` · `n8n` · `Next.js` · `Docker` · `OpenAI API` · `LangGraph` · `MediaPipe` · `YOLO / RKNN` · `FFmpeg`
