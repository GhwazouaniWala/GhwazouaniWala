<div align="center">

<img src="assets/banner.svg" alt="Wala Eddine Ghazouani — AI / Machine Learning Engineer" width="100%"/>

<a href="https://www.walaghazouani.com"><img src="https://img.shields.io/badge/Portfolio-0A192F?style=for-the-badge&logo=googlechrome&logoColor=38BDF8"/></a> <a href="https://www.linkedin.com/in/ghazouani-wala-eddine"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/></a> <a href="https://huggingface.co/Ghazouaniwala"><img src="https://img.shields.io/badge/Hugging_Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black"/></a> <a href="mailto:walaghazouani.work@gmail.com"><img src="https://img.shields.io/badge/Email-2563EB?style=for-the-badge&logo=gmail&logoColor=white"/></a> <a href="https://www.upwork.com/freelancers/~walaghazouani"><img src="https://img.shields.io/badge/Upwork-14A800?style=for-the-badge&logo=upwork&logoColor=white"/></a>

</div>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0A192F,50:2563EB,100:38BDF8&height=3&section=header"/>

## `>` whoami

**Wala Eddine Ghazouani** — final-year Data Science engineering student at **ESPRIT**, Tunis.

I build LLM, RAG and multimodal systems and take them the whole way: fine-tuning the model, designing the retrieval layer, getting inference fast enough to be used live, and putting monitoring and fallback paths around it so it survives contact with real users. Not notebooks that worked once.

<div align="center">

|  |  |
|:--|:--|
| **Available** | January – June 2027 — 6-month final-year engineering internship (PFE) |
| **Based in** | Tunis, Tunisia |
| **Relocation** | Europe · Canada |
| **Languages** | Arabic (native) · French (C1) · English (C1) |

</div>

### What I've done so far

<div align="center">

|  |  |
|:--|:--|
| **Two AI internships** | **Wevioo** — digital-transformation consultancy operating in 30+ countries. The second shipped a real-time multimodal system. |
| **Two published models** | Fine-tuned and released on Hugging Face: 7-class speech-emotion recognition, and Tunisian-Derja speech synthesis. |
| **Project lead, 6 engineers** | Five months on a multi-agent financial platform, delivered with industry partner **VALUE**. |
| **Freelance since 2025** | RAG systems, AI agents and workflow automation for international clients on Upwork — scoping through deployment and handover. |

<img src="assets/capabilities.svg" alt="AI capability map" width="100%"/>

</div>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0A192F,50:2563EB,100:38BDF8&height=3&section=header"/>

## `>` roles I'm targeting

<div align="center">

| Role | What backs it |
|:--|:--|
| **AI / Machine Learning Engineer** | Two AI internships; four systems taken from model to deployed application with monitoring on them. |
| **LLM · Generative AI · RAG Engineer** | Retrieval layers over clinical literature, financial news, UX research and product catalogues. Self-hosted Llama 3.1 70B on vLLM in production. |
| **AI Agent · Agentic Systems Engineer** | LangGraph `StateGraph` orchestration with parallel fan-out, custom state reducers, confidence gates and deterministic fallbacks. Multi-agent platforms in two domains. |
| **Computer Vision · Multimodal · Speech AI** | Concurrent face and voice emotion classification, handwritten Arabic OCR, ONNX-optimised real-time inference. Two speech models published. |

Also a fit for **Applied Scientist**, **MLOps / LLMOps**, **Inference Optimisation** and **Forward-Deployed AI Engineer** roles.

</div>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0A192F,50:2563EB,100:38BDF8&height=3&section=header"/>

## `>` featured work

### [Solace](https://github.com/GhwazouaniWala/Solace) — real-time multimodal AI coach

A coaching system you talk to. Facial expression (EfficientNet-B0, exported to ONNX) and vocal tone (fine-tuned wav2vec2-XLSR-53) are classified **concurrently** while you speak, and replies are grounded by retrieval over **603 clinical documents**, cited by named technique.

**The design decision that matters:** when the two emotion channels disagree — wording reads `neutral`, voice reads `fearful` — the system surfaces the conflict instead of averaging it away. That disagreement is the most informative signal it can produce, and averaging destroys it.

**The engineering problem:** a conversational system is unusable above a certain latency, and running two classifiers plus retrieval plus generation serially blew that budget. Restructuring the pipeline for streaming and parallel execution cut end-to-end latency **4.1×**.

<div align="center">
<table>
<tr>
<td width="50%"><img src="https://raw.githubusercontent.com/GhwazouaniWala/Solace/main/docs/screenshots/voice-mode.png" alt="Solace voice mode"/><br/><b>Voice mode</b> — orb driven by live FFT of the audio stream</td>
<td width="50%"><img src="https://raw.githubusercontent.com/GhwazouaniWala/Solace/main/docs/screenshots/report.png" alt="Solace session report"/><br/><b>Session report</b> — every metric labelled <code>Measured</code> or <code>Model estimate</code></td>
</tr>
</table>
</div>

<details><summary><b>More detail</b></summary><br/>

- Full-duplex voice over WebSocket, so the user can interrupt mid-response.
- Language is followed per turn — switch mid-session and the next reply comes back in the new one, synthesised voice included.
- The session report marks what was measured against what was inferred, so nothing estimated is presented as observed.
- The two emotion classifiers ship as separate models rather than one fused head, so a failure in one channel degrades the output instead of corrupting it.

</details>

<div align="center">
<img src="https://img.shields.io/badge/RAG-2563EB?style=flat-square"/> <img src="https://img.shields.io/badge/Multimodal-2563EB?style=flat-square"/> <img src="https://img.shields.io/badge/wav2vec2--XLSR--53-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/EfficientNet--B0-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/ONNX_Runtime-0A192F?style=flat-square&logo=onnx&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/FastAPI-0A192F?style=flat-square&logo=fastapi&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/ChromaDB-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/WebSockets-0A192F?style=flat-square&logo=socketdotio&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/React-0A192F?style=flat-square&logo=react&logoColor=38BDF8"/>
</div>

---

### [FX AlphaLab](https://github.com/GhwazouaniWala/FX-AlphaLab) — multi-agent financial intelligence platform

Technical, macroeconomic and sentiment agents each analyse major FX pairs from their own data and reach their own conclusion. An orchestrator combines them behind a **conviction gate whose entire purpose is to suppress signals the agents disagree on** — in a domain where a confident wrong answer costs more than no answer at all.

**My role:** **project lead of six engineers over five months**, an ESPRIT integrated engineering project delivered with industry partner VALUE. I owned the macroeconomic agent end to end — ingestion, feature engineering, market-regime detection, training, orchestration — and built the MLOps layer the whole team deployed on.

**What that layer is:** separate Docker images for training and serving so the serving path stays small, MLflow tracking so runs are comparable rather than remembered, Prometheus monitoring, and a backtesting harness reporting win rate, profit factor, drawdown and Sharpe ratio. Unified feature matrix of **204k+ rows spanning 2015–2025**.

<div align="center">
<img src="https://img.shields.io/badge/Multi--Agent-2563EB?style=flat-square"/> <img src="https://img.shields.io/badge/MLOps-2563EB?style=flat-square"/> <img src="https://img.shields.io/badge/PyTorch-0A192F?style=flat-square&logo=pytorch&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/XGBoost-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/MLflow-0A192F?style=flat-square&logo=mlflow&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/Prometheus-0A192F?style=flat-square&logo=prometheus&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/Docker-0A192F?style=flat-square&logo=docker&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/FastAPI-0A192F?style=flat-square&logo=fastapi&logoColor=38BDF8"/>
</div>

---

### [Critiq](https://github.com/GhwazouaniWala/Critiq) — multi-agent UX and conversion audit

Point it at a site and it returns a scored, evidenced UX audit in **under 3 minutes**. Six specialist agents fan out from a LangGraph `StateGraph` using `Send()` with a custom state reducer, scoring **14 weighted dimensions** grounded in a ChromaDB corpus of published UX research (NN/g, Baymard, WCAG 2.1) rather than the model's opinion.

**The reliability design:** every dimension sits behind a confidence gate with a deterministic heuristic fallback, so a slow or failed agent costs one dimension's precision rather than the whole report. Self-hosted Llama 3.1 70B on vLLM runs behind retries and a circuit breaker. The report always ships — and states per dimension which score came from the model and which from the fallback.

Weights adapt to site type: a trust badge matters more on an ecommerce checkout than on a portfolio. Hybrid Playwright and Firecrawl scraping runs under a single `asyncio.gather`, so wall time is the slowest fetch, not the sum of them.

<div align="center">
<table>
<tr>
<td width="50%"><img src="https://raw.githubusercontent.com/GhwazouaniWala/Critiq/master/docs/screenshots/report-radar-dark.png" alt="Critiq 14-dimension radar"/><br/><b>14-dimension radar</b> — real run against stripe.com, 88/100</td>
<td width="50%"><img src="https://raw.githubusercontent.com/GhwazouaniWala/Critiq/master/docs/screenshots/report-top-fixes-dark.png" alt="Critiq top fixes"/><br/><b>Top fixes</b> — ranked by weight × deficit, each with DOM evidence</td>
</tr>
</table>
</div>

<div align="center">
<img src="https://img.shields.io/badge/Agentic_AI-2563EB?style=flat-square"/> <img src="https://img.shields.io/badge/Self--hosted_LLM-2563EB?style=flat-square"/> <img src="https://img.shields.io/badge/LangGraph-0A192F?style=flat-square&logo=langgraph&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/vLLM-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/Llama_3.1_70B-0A192F?style=flat-square&logo=meta&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/ChromaDB-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/Playwright-0A192F?style=flat-square&logo=playwright&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/React-0A192F?style=flat-square&logo=react&logoColor=38BDF8"/>
</div>

---

### [Wathiqa](https://github.com/GhwazouaniWala/Wathiqa) — offline Arabic handwritten document intelligence

Handwritten Tunisian legal forms become structured, searchable client records — **entirely offline**, because privileged client data under Tunisia's INPDP regime cannot be sent to a cloud OCR API. That constraint drove the architecture.

A TrOCR vision-encoder/decoder adapted to handwritten Tunisian Arabic with a **30k-token Arabic vocabulary**. Template matching locates each field and routes it to a purpose-built recogniser — handwriting, numerals, checkboxes and signatures are genuinely different problems — with pages registered beforehand by SIFT keypoints and RANSAC homography, so a scan that is skewed or offset still lines up. Human corrections are retained as labelled training data.

Multi-tenant isolation is enforced **structurally at the session layer**, not by filtering inside queries, with an append-only audit log and **123 tests** including cross-tenant access checks.

<div align="center">
<img src="https://img.shields.io/badge/Computer_Vision-2563EB?style=flat-square"/> <img src="https://img.shields.io/badge/Offline--first-2563EB?style=flat-square"/> <img src="https://img.shields.io/badge/Multi--tenant-2563EB?style=flat-square"/> <img src="https://img.shields.io/badge/TrOCR-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/PyTorch-0A192F?style=flat-square&logo=pytorch&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/OpenCV-0A192F?style=flat-square&logo=opencv&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/SQLAlchemy-0A192F?style=flat-square&logo=sqlalchemy&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/pytest-0A192F?style=flat-square&logo=pytest&logoColor=38BDF8"/>
</div>

---

<details><summary><b>Earlier work</b></summary><br/>

**[NeuraShop](https://github.com/GhwazouaniWala/NeuraShop) — accessible AI marketplace.** Six deep-learning modules fire the moment a seller uploads a photo, so nobody fills in a form: auto-categorisation (**97.4% F1** across 14 classes — my module), WCAG-validated alt-text via BLIP so screen-reader users aren't locked out, a photo-quality gate with a CNN enhancer fallback, aspect-based review sentiment, visual recommendations and a RAG shopping assistant.

**[MeetSummary](https://github.com/GhwazouaniWala/Summify) — self-hosted Teams meeting summariser.** Microsoft Graph OAuth 2.0, automatic discovery of OneDrive recordings, Whisper transcription, LLM summarisation and PDF export. Delivered solo across three Scrum sprints (18 user stories, UML) on a hybrid JavaFX + Flask architecture with a REST bridge and a MySQL data model. Built during my first Wevioo internship.

</details>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0A192F,50:2563EB,100:38BDF8&height=3&section=header"/>

## `>` published models

<div align="center">

| Model | What it is | Why it exists | |
|:--|:--|:--|:--|
| **`emotions_speech`** | wav2vec2-large-XLSR-53 fine-tuned for 7-class speech-emotion recognition | Evaluated **speaker-independently** with `GroupKFold` — a random split leaks speaker identity and inflates the numbers usually reported | [![HF](https://img.shields.io/badge/🤗_model-FFD21E?style=flat-square)](https://huggingface.co/Ghazouaniwala/emotions_speech) |
| **`silma-tts-derja`** | F5-TTS fine-tuned for **Tunisian Derja** speech synthesis | Off-the-shelf Arabic TTS outputs Modern Standard Arabic, a register almost nobody speaks conversationally | [![HF](https://img.shields.io/badge/🤗_model-FFD21E?style=flat-square)](https://huggingface.co/Ghazouaniwala/silma-tts-derja) |

</div>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0A192F,50:2563EB,100:38BDF8&height=3&section=header"/>

## `>` experience

```
2026 · Jun–Aug   AI Engineering Intern — Wevioo, Tunis
                 Designed and shipped Solace. Fine-tuned and published two
                 speech models to Hugging Face. Cut end-to-end inference
                 latency 4.1x via streaming and parallel execution.

2026 · Feb–Jun   Project Lead — FX AlphaLab (ESPRIT x VALUE)
                 Led 6 engineers over 5 months. Owned the macroeconomic
                 agent end to end and built the platform's MLOps layer.

2025 · Present   AI Engineer, Freelance — Upwork
                 RAG chatbots over client knowledge bases, Python AI agents
                 and workflow automation, scraping-to-structured pipelines.
                 Scoping through deployment, integration and handover.

2025 · Jul–Aug   Software Engineering Intern — Wevioo, Tunis
                 MeetSummary, solo across 3 Scrum sprints: Graph OAuth 2.0,
                 OneDrive discovery, Whisper, LLM summarisation, PDF export.
```

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0A192F,50:2563EB,100:38BDF8&height=3&section=header"/>

## `>` how I work

**Systems degrade, they don't fall over.** Every system above has a fallback path, so a failed model or a dead API costs quality rather than availability.

**Numbers come with their measurement.** Reported figures state how they were obtained — speaker-independent, not a random split — and outputs mark what was inferred rather than observed.

**Limitations are written down.** Each repository documents where it falls short. Knowing the failure modes is part of having built the thing.

<div align="center">
<img src="assets/pipeline.svg" alt="How I build — understand, model, evaluate, serve, monitor, ship" width="100%"/>
</div>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0A192F,50:2563EB,100:38BDF8&height=3&section=header"/>

## `>` stack

<div align="center">

**Generative AI · LLMs**

<img src="https://img.shields.io/badge/PyTorch-0A192F?style=flat-square&logo=pytorch&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/Transformers-0A192F?style=flat-square&logo=huggingface&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/PEFT_%2F_LoRA-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/vLLM-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/Llama_3.1-0A192F?style=flat-square&logo=meta&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/Ollama-0A192F?style=flat-square&logo=ollama&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/F5--TTS-0A192F?style=flat-square"/>

**Agents · Orchestration · RAG**

<img src="https://img.shields.io/badge/LangGraph-0A192F?style=flat-square&logo=langgraph&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/LangChain-0A192F?style=flat-square&logo=langchain&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/ChromaDB-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/FAISS-0A192F?style=flat-square&logo=meta&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/sentence--transformers-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/MCP-0A192F?style=flat-square&logo=anthropic&logoColor=38BDF8"/>

**Vision · Speech · Multimodal**

<img src="https://img.shields.io/badge/OpenCV-0A192F?style=flat-square&logo=opencv&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/ONNX_Runtime-0A192F?style=flat-square&logo=onnx&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/EfficientNet--B0-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/wav2vec2--XLSR--53-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/Whisper-0A192F?style=flat-square&logo=openai&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/TrOCR-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/librosa-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/spaCy-0A192F?style=flat-square&logo=spacy&logoColor=38BDF8"/>

**ML · Data**

<img src="https://img.shields.io/badge/Python-0A192F?style=flat-square&logo=python&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/scikit--learn-0A192F?style=flat-square&logo=scikitlearn&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/XGBoost-0A192F?style=flat-square"/> <img src="https://img.shields.io/badge/NumPy-0A192F?style=flat-square&logo=numpy&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/pandas-0A192F?style=flat-square&logo=pandas&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/SQL-0A192F?style=flat-square&logo=postgresql&logoColor=38BDF8"/>

**Serving · MLOps · Infra**

<img src="https://img.shields.io/badge/FastAPI-0A192F?style=flat-square&logo=fastapi&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/WebSockets-0A192F?style=flat-square&logo=socketdotio&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/Flask-0A192F?style=flat-square&logo=flask&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/Pydantic-0A192F?style=flat-square&logo=pydantic&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/SQLAlchemy-0A192F?style=flat-square&logo=sqlalchemy&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/PostgreSQL-0A192F?style=flat-square&logo=postgresql&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/Docker-0A192F?style=flat-square&logo=docker&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/MLflow-0A192F?style=flat-square&logo=mlflow&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/Prometheus-0A192F?style=flat-square&logo=prometheus&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/GitHub_Actions-0A192F?style=flat-square&logo=githubactions&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/Linux-0A192F?style=flat-square&logo=linux&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/Git-0A192F?style=flat-square&logo=git&logoColor=38BDF8"/>

**Interfaces**

<img src="https://img.shields.io/badge/React-0A192F?style=flat-square&logo=react&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/TypeScript-0A192F?style=flat-square&logo=typescript&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/Tailwind-0A192F?style=flat-square&logo=tailwindcss&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/Vite-0A192F?style=flat-square&logo=vite&logoColor=38BDF8"/> <img src="https://img.shields.io/badge/Streamlit-0A192F?style=flat-square&logo=streamlit&logoColor=38BDF8"/>

</div>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0A192F,50:2563EB,100:38BDF8&height=3&section=header"/>

## `>` education & certifications

**Engineering Degree in Computer Science — Data Science** · ESPRIT, Tunis · Sep 2024 – Jun 2027
**Preparatory Cycle for Engineering Studies, Mathematics & Physics** · IPEI Bizerte · Sep 2022 – Jun 2024

<div align="center">

| Certification | Provider | Issued |
|:--|:--|:--|
| [Fundamentals of Deep Learning](https://learn.nvidia.com/certificates) | NVIDIA Deep Learning Institute | Jan 2026 |
| [Building AI Agents with Multimodal Models](https://learn.nvidia.com/certificates?id=JOcvsCL5R_COA2qjS-_V1Q) | NVIDIA Deep Learning Institute | Jan 2025 |
| [Generative AI with Diffusion Models](https://learn.nvidia.com/certificates?id=-5GEyfimSQme_gwlTRSCsw) | NVIDIA Deep Learning Institute | Jan 2025 |
| [LLM Engineering in Practice](https://learn.365datascience.com/c/7075d10c57) | 365 Data Science | Mar 2026 |
| [Convolutional Neural Networks with TensorFlow](https://learn.365datascience.com/c/b7907b56fe) | 365 Data Science | Nov 2025 |

All credentials are independently verifiable at the links above.

</div>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0A192F,50:2563EB,100:38BDF8&height=3&section=header"/>

<div align="center">

## `>` contact me about an internship

**Seeking a 6-month final-year AI engineering internship — January to June 2027**

LLMs · RAG · Agents · Vision · Multimodal · MLOps
Open to relocation — Europe | Canada

<br/>

<a href="mailto:walaghazouani.work@gmail.com"><img src="https://img.shields.io/badge/📧_walaghazouani.work@gmail.com-2563EB?style=for-the-badge"/></a> <a href="https://www.linkedin.com/in/ghazouani-wala-eddine"><img src="https://img.shields.io/badge/💼_LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/></a> <a href="https://huggingface.co/Ghazouaniwala"><img src="https://img.shields.io/badge/🤗_Hugging_Face-FFD21E?style=for-the-badge"/></a> <a href="https://www.walaghazouani.com"><img src="https://img.shields.io/badge/🌐_Portfolio-0A192F?style=for-the-badge"/></a>

<br/><br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:04070F,40:1E3A8A,100:38BDF8&height=120&section=footer"/>

</div>
