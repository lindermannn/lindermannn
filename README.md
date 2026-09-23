## Dimitry Donaire — Applied AI Engineer

I build and operate AI systems: a multi-tenant conversational platform, a production RAG pipeline with a measured evaluation harness, and computer vision running on edge hardware. My work covers deployment, measurement, failure recovery and cost control.

**Ovalle, Chile · Open to remote roles** · [Email](mailto:dimitrydonaire@gmail.com) · [LinkedIn](https://linkedin.com/in/dimitry-donaire-6828aa400)

### Selected work

**[NUMEN AI](https://github.com/lindermannn/numen-platform)** · [Product](https://numen-ai.cl) — multi-tenant conversational AI platform in production. WhatsApp, Telegram and Web Chat are live; Instagram DM and Messenger are connected and awaiting Meta App Review for public rollout. Tenant isolation, RAG, spend caps and operator takeover are documented in the public architecture. In a pre-commercial configuration, idle executions fell by about 90%: ~9,330/month extrapolated from three measured days to ~936/month expected from the revised schedules. [Method and limits](https://github.com/lindermannn/numen-platform/blob/master/docs/finops.md).

**[Huberman RAG](https://github.com/lindermannn/huberman-rag-eval)** · [Live demo](https://production-hybrid-rag.lovable.app) — production retrieval over 27,254 chunks from roughly 417 podcast episodes. Hybrid search, query rewriting and reranking are evaluated on a 42-question set: **Recall@8 78.1%**, **MRR 0.593**. The repository includes the harness, CI tests and an account of a finding withdrawn after discovering that the evaluation judge truncated its own input. [Evaluation and limitations](https://github.com/lindermannn/huberman-rag-eval/blob/main/docs/EVALUATION.md).

**[Numen Vision](https://github.com/lindermannn/edge-ai-surveillance)** — edge video analytics that evolved from a multi-camera prototype for public tenders into a residential appliance. The private implementation now runs YOLOX-Nano through RKNN on an RK3576 NPU. A recorded **7.85-hour board run** processed four replayed 4 MP H.265 sources at **3.84 analysed fps per camera**; physical cameras and a 24-hour run remain untested. The public repository provides the architecture, measurement method and limits; implementation and deployment configuration remain private.

**[BermGuard](https://github.com/lindermannn/bermguard-ai-vision-pipeline)** — a six-day technical exercise in mining vehicle and berm monitoring. The public repository documents segmentation, temporal tracking, geometry, validation decisions and limitations. The submitted implementation and source videos are private.

### Background

Before AI engineering, I spent over eight years in mining, power generation and industrial construction (2016–2025). That experience informs how I design for failure and document evidence. I also publish negative results: in Huberman RAG, I withdrew an evaluation finding after measuring bias in the judge rather than defending a favorable number.

- **Languages:** Python · TypeScript · JavaScript/Node · SQL
- **Data and infrastructure:** PostgreSQL/pgvector · Supabase · Docker · n8n · Next.js
- **AI and vision:** RAG evaluation · OpenAI API · YOLO/RKNN · OpenCV · MediaPipe · FFmpeg
