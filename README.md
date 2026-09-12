<p align="center">
  <img src="assets/banner.svg" alt="Wala Eddine Ghazouani — AI / Machine Learning Engineer" width="100%">
</p>

<h1 align="center">Wala Eddine Ghazouani</h1>

<p align="center">
  <b>AI / Machine Learning Engineer</b><br>
  Final-year Data Science engineering student · ESPRIT, Tunis
</p>

<p align="center">
  <a href="https://www.walaghazouani.com">Portfolio</a> ·
  <a href="https://www.linkedin.com/in/ghazouani-wala-eddine">LinkedIn</a> ·
  <a href="https://huggingface.co/Ghazouaniwala">Hugging Face</a> ·
  <a href="https://www.walaghazouani.com/Wala_Eddine_Ghazouani_CV.pdf">CV</a> ·
  <a href="mailto:walaghazouani.work@gmail.com">walaghazouani.work@gmail.com</a>
</p>

---

I build LLM, RAG and multimodal systems, and I take them the whole way: fine-tuning the model, designing the retrieval layer, getting inference fast enough to be used live, and putting monitoring and fallbacks around it so it survives contact with real users.

**Seeking a 6-month final-year engineering internship, January – June 2027.** Open to relocation across Europe and Canada.

**Track record so far**

| | |
|---|---|
| **Two AI internships** | Wevioo — a digital-transformation consultancy operating in 30+ countries. The second built a real-time multimodal system in production. |
| **Two published models** | Fine-tuned and released on Hugging Face: 7-class speech-emotion recognition, and Tunisian-Derja speech synthesis. |
| **Project lead, 6 engineers** | Five months on a multi-agent financial platform, delivered with industry partner VALUE. |
| **Freelance since 2025** | RAG systems, AI agents and automation for international clients on Upwork — scoping through deployment and handover. |

---

## Featured work

### [Solace](https://github.com/GhwazouaniWala/Solace) — real-time multimodal AI coach

A coaching system you talk to. Facial expression (EfficientNet-B0, exported to ONNX) and vocal tone (fine-tuned wav2vec2-XLSR-53) are classified **concurrently** while you speak, and the model's replies are grounded by retrieval over 603 clinical documents, cited by named technique.

**The design decision that matters:** when the two emotion channels disagree — wording reads `neutral`, voice reads `fearful` — the system surfaces the conflict instead of averaging it away. That disagreement is the most informative signal it can produce, and averaging destroys it.

**The engineering problem:** a conversational system is unusable above a certain latency, and running two classifiers plus retrieval plus generation serially blew that budget. Restructuring the pipeline for streaming output and parallel execution brought end-to-end latency down **4.1×**.

<p>
  <img src="https://raw.githubusercontent.com/GhwazouaniWala/Solace/main/docs/screenshots/voice-mode.png" alt="Solace voice mode — orb driven by live FFT of the audio stream" width="49%">
  <img src="https://raw.githubusercontent.com/GhwazouaniWala/Solace/main/docs/screenshots/report.png" alt="Solace session report — every metric labelled Measured or Model estimate" width="49%">
</p>

<details>
<summary>More detail</summary>

- Full-duplex voice over WebSocket, so the user can interrupt mid-response.
- Language is followed per turn: switch mid-session and the next reply comes back in the new language, synthesised voice included.
- The session report labels every metric `Measured` or `Model estimate`, so nothing inferred is presented as observed.
- Both emotion classifiers ship as separate models rather than one fused head, so a failure in one channel degrades the output instead of corrupting it.

</details>

`Python` · `PyTorch` · `wav2vec2-XLSR-53` · `EfficientNet-B0` · `ONNX Runtime` · `ChromaDB` · `FastAPI` · `WebSocket` · `React`

---

### [FX AlphaLab](https://github.com/GhwazouaniWala/FX-AlphaLab) — multi-agent financial intelligence platform

Technical, macroeconomic and sentiment agents each analyse major FX pairs from their own data and reach their own conclusion. An orchestrator combines them behind a **conviction gate whose entire purpose is to suppress signals the agents disagree on** — in a domain where a confident wrong answer costs more than no answer.

**My role:** project lead of six engineers over five months, an ESPRIT integrated engineering project delivered with industry partner VALUE. I owned the macroeconomic agent end to end — ingestion, feature engineering, market-regime detection, training, orchestration — and built the MLOps layer the whole team deployed on.

**What that MLOps layer is:** separate Docker images for training and serving so the serving path stays small, MLflow tracking so runs are comparable rather than remembered, Prometheus monitoring, and a backtesting harness reporting win rate, profit factor, drawdown and Sharpe ratio. Unified feature matrix of **204k+ rows spanning 2015–2025**.

`Python` · `PyTorch` · `XGBoost` · `scikit-learn` · `ChromaDB` · `FastAPI` · `MLflow` · `Prometheus` · `Docker`

---

### [Critiq](https://github.com/GhwazouaniWala/Critiq) — multi-agent UX and conversion audit

Point it at a site and it returns a scored, evidenced UX audit in under three minutes. Six specialist agents fan out from a LangGraph `StateGraph` using `Send()` with a custom state reducer, scoring **14 weighted dimensions** grounded in a ChromaDB corpus of published UX research (NN/g, Baymard, WCAG 2.1) rather than the model's opinion.

**The reliability design:** every dimension sits behind a confidence gate with a deterministic heuristic fallback, so a slow or failed agent costs one dimension's precision rather than the whole report. Self-hosted Llama 3.1 70B on vLLM runs behind retries and a circuit breaker. The report always ships, and it states per dimension which score came from the model and which from the fallback.

Weights adapt to site type — a trust badge matters more on an ecommerce checkout than on a portfolio. Hybrid Playwright and Firecrawl scraping runs under a single `asyncio.gather`, so wall time is the slowest fetch, not the sum of them.

<p>
  <img src="https://raw.githubusercontent.com/GhwazouaniWala/Critiq/master/docs/screenshots/report-radar-dark.png" alt="Critiq 14-dimension radar — real run against stripe.com" width="49%">
  <img src="https://raw.githubusercontent.com/GhwazouaniWala/Critiq/master/docs/screenshots/report-top-fixes-dark.png" alt="Critiq top fixes — ranked by weight × deficit, each with DOM evidence" width="49%">
</p>

`Python` · `LangGraph` · `vLLM` · `Llama 3.1 70B` · `ChromaDB` · `FastAPI` · `Playwright` · `React`

---

### [Wathiqa](https://github.com/GhwazouaniWala/Wathiqa) — offline Arabic handwritten document intelligence

Handwritten Tunisian legal forms become structured, searchable client records — **entirely offline**, because privileged client data under Tunisia's INPDP regime cannot be sent to a cloud OCR API. That constraint drove the architecture: no managed service, everything on-premise.

A TrOCR vision-encoder/decoder adapted to handwritten Tunisian Arabic with a 30k-token Arabic vocabulary. Template matching locates each field and routes it to a purpose-built recogniser — handwriting, numerals, checkboxes and signatures are genuinely different problems — with pages registered beforehand by SIFT keypoints and RANSAC homography so a scan that is skewed or offset still lines up. Human corrections are retained as labelled training data.

Multi-tenant isolation is enforced **structurally at the session layer**, not by filtering in queries, with an append-only audit log and 123 tests including cross-tenant access checks.

`Python` · `TrOCR` · `PyTorch` · `OpenCV` · `EasyOCR` · `FastAPI` · `SQLAlchemy` · `pytest`

---

<details>
<summary><b>Earlier work</b></summary>

**[NeuraShop](https://github.com/GhwazouaniWala/NeuraShop) — accessible AI marketplace.** Six deep-learning modules fire the moment a seller uploads a photo, so nobody fills in a form: auto-categorisation (**97.4% F1** across 14 classes — my module), WCAG-validated alt-text via BLIP so screen-reader users aren't locked out, a photo-quality gate with a CNN enhancer fallback, aspect-based review sentiment, visual recommendations and a RAG shopping assistant.

**[MeetSummary](https://github.com/GhwazouaniWala/Summify) — self-hosted Teams meeting summariser.** Microsoft Graph OAuth 2.0, automatic discovery of OneDrive recordings, Whisper transcription, LLM summarisation and PDF export. Delivered solo across three Scrum sprints (18 user stories, UML) on a hybrid JavaFX + Flask architecture with a REST bridge and a MySQL data model. Built during my first Wevioo internship.

</details>

---

## Published models

| Model | What it is | Why it exists |
|---|---|---|
| [`emotions_speech`](https://huggingface.co/Ghazouaniwala/emotions_speech) | wav2vec2-large-XLSR-53 fine-tuned for 7-class speech-emotion recognition | Evaluated **speaker-independently** with `GroupKFold` — a random split leaks speaker identity and inflates the numbers you usually see reported |
| [`silma-tts-derja`](https://huggingface.co/Ghazouaniwala/silma-tts-derja) | F5-TTS fine-tuned for Tunisian Derja speech synthesis | Off-the-shelf Arabic TTS outputs Modern Standard Arabic, a register almost nobody speaks conversationally |

---

## Experience

**AI Engineering Intern — Wevioo, Tunis** · Jun – Aug 2026
Designed and shipped Solace. Fine-tuned and published two speech models to Hugging Face. Cut end-to-end inference latency 4.1× by restructuring the pipeline for streaming and parallel execution.

**Project Lead — FX AlphaLab (ESPRIT × VALUE)** · Feb – Jun 2026
Led six engineers over five months. Owned the macroeconomic agent end to end and built the platform's MLOps layer.

**AI Engineer, Freelance — Upwork** · 2025 – present
RAG chatbots over client knowledge bases, Python AI agents and workflow automation, and scraping pipelines that turn scattered sources into structured data. Scoping through deployment, integration and handover.

**Software Engineering Intern — Wevioo, Tunis** · Jul – Aug 2025
Built MeetSummary solo across three Scrum sprints — Graph OAuth 2.0, OneDrive recording discovery, Whisper transcription, LLM summarisation, PDF export.

---

## How I work

**Systems degrade, they don't fall over.** Every system here has a fallback path, so a failed model or a dead API costs quality rather than availability.

**Numbers come with their measurement.** Reported figures state how they were obtained — speaker-independent, not a random split — and outputs mark what was inferred rather than observed.

**Limitations are written down.** Each repository documents where it falls short. Knowing the failure modes is part of having built the thing.

---

## Stack

**Modelling and fine-tuning** — PyTorch, Hugging Face Transformers, PEFT/LoRA, TensorFlow/Keras, scikit-learn, XGBoost, ONNX Runtime, OpenCV, MediaPipe, librosa, spaCy, wav2vec2, Whisper, TrOCR, F5-TTS, BLIP

**LLM and agent systems** — LangGraph, LangChain, vLLM, Ollama, ChromaDB, FAISS, sentence-transformers, RAG pipelines, Model Context Protocol

**Serving, MLOps and infrastructure** — FastAPI, Flask, WebSocket, Pydantic, SQLAlchemy, Docker, MLflow, Prometheus, GitHub Actions, pytest, Linux, Git

**Languages, data and interfaces** — Python, SQL, Java, C, TypeScript/JavaScript · PostgreSQL, MySQL, Pandas, NumPy, Parquet · React, Vite, Tailwind CSS, Streamlit · Agile/Scrum, UML

---

## Education and certifications

**Engineering Degree in Computer Science — Data Science** · ESPRIT, Tunis · Sep 2024 – Jun 2027
**Preparatory Cycle for Engineering Studies, Mathematics & Physics** · IPEI Bizerte · Sep 2022 – Jun 2024

NVIDIA Deep Learning Institute — Fundamentals of Deep Learning (2026) · Building AI Agents with Multimodal Models (2025) · Generative AI with Diffusion Models (2025)
365 Data Science — LLM Engineering in Practice (2026) · Convolutional Neural Networks with TensorFlow (2025)

Languages: Arabic (native) · French (C1) · English (C1)

---

<p align="center">
  <b>Available January – June 2027 for a 6-month final-year AI engineering internship.</b><br>
  <a href="mailto:walaghazouani.work@gmail.com">walaghazouani.work@gmail.com</a> ·
  <a href="https://www.linkedin.com/in/ghazouani-wala-eddine">LinkedIn</a> ·
  <a href="https://www.walaghazouani.com">walaghazouani.com</a>
</p>
