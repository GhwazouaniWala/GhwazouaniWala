<p align="center">
  <img src="assets/banner.svg" alt="Wala Eddine Ghazouani — AI / Machine Learning Engineer" width="100%">
</p>

# Wala Eddine Ghazouani

**AI / Machine Learning Engineer · Final-year Data Science engineering student, ESPRIT (Tunis)**

I build LLM, RAG and multimodal systems and take them through to a deployed, monitored application — fine-tuning, retrieval, real-time inference and the MLOps around it.

**Available January – June 2027 for a 6-month final-year internship. Open to relocation across Europe and Canada; internship agreement issued by ESPRIT.**

[Portfolio](https://www.walaghazouani.com) · [LinkedIn](https://www.linkedin.com/in/ghazouani-wala-eddine) · [Hugging Face](https://huggingface.co/Ghazouaniwala) · [CV (PDF)](https://www.walaghazouani.com/Wala_Eddine_Ghazouani_CV.pdf) · walaghazouani.work@gmail.com

---

## In short

- Two AI internships at **Wevioo** (digital-transformation consultancy, 30+ countries); the second shipped a real-time multimodal coaching system and cut its inference latency **4.1×**.
- **Two fine-tuned speech models published** on Hugging Face: a 7-class speech-emotion classifier and a Tunisian-Derja text-to-speech model.
- **Project lead** of a six-person team over five months on a multi-agent financial platform delivered with industry partner VALUE.
- Freelance AI engineer on Upwork since 2025: RAG chatbots, Python agents and scraping pipelines for international clients, scoped through to handover.

---

## Featured work

### [Solace](https://github.com/GhwazouaniWala/Solace) — real-time multimodal AI coach

Full-duplex voice over WebSocket, with facial (EfficientNet-B0 on ONNX) and vocal (fine-tuned wav2vec2-XLSR-53) emotion classifiers running concurrently. Answers are grounded by RAG over 603 clinical documents and cited by technique. Disagreement between the two emotion channels is surfaced to the user rather than averaged. Restructuring the pipeline for streaming and parallel execution reduced end-to-end latency 4.1×.

<p>
  <img src="https://raw.githubusercontent.com/GhwazouaniWala/Solace/main/docs/screenshots/voice-mode.png" alt="Solace voice mode" width="49%">
  <img src="https://raw.githubusercontent.com/GhwazouaniWala/Solace/main/docs/screenshots/report.png" alt="Solace session report" width="49%">
</p>

`Python` `PyTorch` `wav2vec2` `ONNX Runtime` `ChromaDB` `FastAPI` `WebSocket` `React`

### [FX AlphaLab](https://github.com/GhwazouaniWala/FX-AlphaLab) — multi-agent financial intelligence platform

Technical, macroeconomic and sentiment agents analyse major FX pairs independently; an orchestrator and a conviction gate suppress signals the agents disagree on. Unified feature matrix of 204k+ rows (2015–2025). I led the six-person team, owned the macro agent end to end (ingestion, feature engineering, regime detection, training, orchestration) and set up the MLOps layer: separate Docker images for training and serving, MLflow tracking, Prometheus monitoring, and backtesting on win rate, profit factor, drawdown and Sharpe.

`Python` `PyTorch` `XGBoost` `scikit-learn` `ChromaDB` `FastAPI` `MLflow` `Prometheus` `Docker`

### [Critiq](https://github.com/GhwazouaniWala/Critiq) — multi-agent UX and brand audit

Six specialist agents run in parallel under a LangGraph StateGraph and score 14 weighted UX dimensions against a ChromaDB corpus of published UX research (NN/g, Baymard, WCAG 2.1). Self-hosted Llama 3.1 70B on vLLM sits behind retries, a circuit breaker and a deterministic heuristic fallback per dimension, so a full audit always completes — in under 3 minutes.

<p>
  <img src="https://raw.githubusercontent.com/GhwazouaniWala/Critiq/master/docs/screenshots/report-radar-dark.png" alt="Critiq 14-dimension radar" width="49%">
  <img src="https://raw.githubusercontent.com/GhwazouaniWala/Critiq/master/docs/screenshots/report-top-fixes-dark.png" alt="Critiq top fixes" width="49%">
</p>

`Python` `LangGraph` `vLLM` `Llama 3.1 70B` `ChromaDB` `FastAPI` `Playwright` `React`

### [Wathiqa](https://github.com/GhwazouaniWala/Wathiqa) — offline Arabic handwritten document recognition

Turns handwritten Tunisian legal forms into structured records without any cloud API, so privileged client data stays on-premise. A TrOCR vision-encoder/decoder adapted to handwritten Tunisian Arabic (30k-token vocabulary), with each field type routed to a dedicated engine and pages registered by SIFT keypoints and RANSAC homography. Multi-tenant isolation is enforced at the session layer with an append-only audit log; 123 tests including cross-tenant checks.

`Python` `TrOCR` `PyTorch` `OpenCV` `EasyOCR` `FastAPI` `SQLAlchemy` `pytest`

---

## Published models

| Model | Description |
|---|---|
| [`emotions_speech`](https://huggingface.co/Ghazouaniwala/emotions_speech) | wav2vec2-large-XLSR-53 fine-tuned for 7-class speech-emotion recognition; evaluated speaker-independently with GroupKFold. |
| [`silma-tts-derja`](https://huggingface.co/Ghazouaniwala/silma-tts-derja) | F5-TTS fine-tuned for Tunisian Derja speech synthesis, where off-the-shelf Arabic TTS only covers Modern Standard Arabic. |

---

## Experience

**AI Engineering Intern — Wevioo** · Jun – Aug 2026
Built Solace (above). Fine-tuned and published two speech models; cut end-to-end inference latency 4.1×.

**Project Lead — FX AlphaLab (ESPRIT × VALUE)** · Feb – Jun 2026
Led six engineers over five months; owned the macro agent and the MLOps layer.

**AI Engineer, Freelance — Upwork** · 2025 – present
RAG chatbots over client knowledge bases, Python AI agents and workflow automation, scraping-to-structured-data pipelines. Scoping, deployment, integration and handover.

**Software Engineering Intern — Wevioo** · Jul – Aug 2025
Built [MeetSummary](https://github.com/GhwazouaniWala/Summify), a self-hosted Microsoft Teams meeting summariser: Graph OAuth 2.0, automatic OneDrive recording discovery, Whisper transcription, LLM summarisation, PDF export. Delivered solo over three Scrum sprints (18 user stories) on a JavaFX + Flask architecture with a REST bridge and MySQL.

---

## Stack

**Modelling:** PyTorch, Hugging Face Transformers, PEFT/LoRA, TensorFlow/Keras, scikit-learn, XGBoost, ONNX Runtime, OpenCV, wav2vec2, Whisper, TrOCR, F5-TTS
**LLM systems:** LangGraph, LangChain, vLLM, Ollama, ChromaDB, FAISS, sentence-transformers, RAG, MCP
**Serving and MLOps:** FastAPI, Flask, WebSocket, Pydantic, SQLAlchemy, Docker, MLflow, Prometheus, GitHub Actions, pytest, Linux
**Languages and other:** Python, SQL, Java, C, TypeScript; PostgreSQL, MySQL; React, Vite, Tailwind CSS

---

## Certifications

- NVIDIA Deep Learning Institute — Fundamentals of Deep Learning (Jan 2026)
- NVIDIA Deep Learning Institute — Building AI Agents with Multimodal Models (Jan 2025)
- NVIDIA Deep Learning Institute — Generative AI with Diffusion Models (Jan 2025)
- 365 Data Science — LLM Engineering in Practice (Mar 2026)
- 365 Data Science — Convolutional Neural Networks with TensorFlow (Nov 2025)

---

## Education

**Engineering Degree in Computer Science — Data Science** · ESPRIT, Tunis · 2024 – 2027
**Preparatory Cycle, Mathematics and Physics** · IPEI Bizerte · 2022 – 2024

Languages: Arabic (native) · French (C1) · English (C1)

---

**Contact for internships:** walaghazouani.work@gmail.com · [LinkedIn](https://www.linkedin.com/in/ghazouani-wala-eddine) · [walaghazouani.com](https://www.walaghazouani.com)
