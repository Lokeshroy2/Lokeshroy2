# Hi, I'm Lokesh Chandra Roy

AI/ML Engineer building production voice agents, RAG pipelines, and agentic systems.

Currently at **Tecdata IT Services** — shipping a real-time voice AI platform handling 10,000+ daily interactions in production.

Chennai, India · Open to AI/ML Engineer, GenAI Engineer, and NLP Engineer roles.

[LinkedIn](https://www.linkedin.com/in/lokesh-roy02/) · [Email](mailto:lokeshroy523@gmail.com)

---

## What I work on

- **Real-time voice AI** — GPT-4o Realtime API, Gemini Live, Asterisk ARI, RTP audio streaming, VAD/AGC
- **Agentic systems** — LangGraph, multi-agent orchestration, Agent2Agent (A2A) protocol, Model Context Protocol (MCP)
- **RAG & retrieval** — hybrid dense + BM25 retrieval, Pinecone, FAISS, RAGAS-based evaluation
- **Computer vision** — object detection & multi-object tracking, camera calibration / homography for real-world measurement
- **Document intelligence** — OCR + NLP pipelines, structured extraction from unstructured documents
- **Agent safety & evaluation** — adversarial red-teaming, prompt injection testing, statistical validation of ML pipelines

---

## Featured projects

### [A2A + MCP Multi-Agent System](https://github.com/Lokeshroy2)
Two independently implemented agents (OCR-based document agent, rule-based finance agent) that discover each other and exchange tasks purely via the official Agent2Agent protocol — no custom integration code between internals. Verified live agent discovery, task handoff, and error propagation end-to-end.
`A2A Protocol` `MCP` `Tesseract OCR` `Python`

### [Insurance Finance Analysis Agent](https://github.com/Lokeshroy2)
Agent that ingests policy/claims data, flags anomalies via combined rule-based checks + Isolation Forest, and generates natural-language audit reports. Rules alone: 69% precision / 78% recall. Isolation Forest alone: 23% precision. Combined approach: 91% recall.
`Scikit-learn` `Isolation Forest` `LLM Reporting`

### [Agent Red-Teaming Harness](https://github.com/Lokeshroy2)
Built an attack harness that fired 7 adversarial documents at an OCR/field-extraction pipeline — 5 of 7 succeeded on the original code by exploiting first-match field extraction (a fake value planted earlier in a document wins) and a whitespace-validation bypass (blank-looking input read as filled). Fixed both root causes (last-match extraction, whitespace stripping before validation) and re-validated: 0 of 7 attacks succeed, confirmed by a regression test that honest documents still process correctly. Also built a separate LLM prompt-injection/jailbreak test harness for an AI document-reading agent, built and demo-ready pending a live API key for full runs.
`Adversarial Testing` `Prompt Injection` `Security`

### [SQL + Statistical Fraud Detection Pipeline](https://github.com/Lokeshroy2)
Engineered behavioral features from 60,000 transactions using SQL window functions, validated each with Welch's t-test / Chi-square before modeling. XGBoost reached 76% precision / 94.6% recall under 1.5% class imbalance — deployed behind a load-tested FastAPI service (438.8 req/sec, 0 errors).
`SQL` `SciPy` `XGBoost` `FastAPI`

### [Retail Sales Forecasting](https://github.com/Lokeshroy2)
Decomposed 3 years of daily sales data, validated stationarity with the Augmented Dickey-Fuller test, and compared Seasonal Naive, Holt-Winters, and SARIMA. Holt-Winters gave the best result (8.36% MAPE) — with an honest diagnosis of where all models under-predicted holiday-season spikes.
`Statsmodels` `Pandas` `Time Series`

### [Multi-Agent Research Pipeline](https://github.com/Lokeshroy2)
LangGraph-coordinated multi-agent system (search, summarization, fact-checking) with structured hand-off between agents, benchmarked using the RAGAS framework — faithfulness 0.87, relevance 0.91.
`LangGraph` `LangChain` `RAGAS`

### [Vehicle Speed Estimation](https://github.com/Lokeshroy2)
A computer-vision pipeline that detects vehicles with YOLOv8, tracks them across frames with ByteTrack to give each vehicle a stable ID, and estimates real-world speed from pixel displacement over time. Supports homography-based camera calibration (4 reference points mapped to real road coordinates) for accurate perspective-corrected speed, in addition to a simple fixed pixel-to-meter scale.
`YOLOv8` `ByteTrack` `OpenCV` `Camera Calibration` `Python`

### [Local Multi-Document RAG Chatbot](https://github.com/Lokeshroy2)
A fully local RAG chatbot — upload PDF/TXT/Markdown files and ask questions answered from their content, with no cloud LLM or API key required. Chunks documents, embeds them with Sentence-Transformers (`all-MiniLM-L6-v2`), indexes with FAISS, and generates cited, streamed answers via Ollama/Mistral 7B. Includes conversational query rewriting for follow-up questions and a retrieval evaluation harness (100% hit@5 on a 13-question golden set).
`FastAPI` `Sentence-Transformers` `FAISS` `Ollama` `Mistral`

---

## In production at Tecdata IT Services

- **Speech AI & agentic voice platform** — GPT-4o Realtime API, autonomous intent reasoning, human-in-the-loop escalation, multilingual (Tamil, Hindi, Kannada, Telugu), 10,000+ daily interactions at sub-2.5s latency
- **Document intelligence pipeline** — dual-path OCR (Tesseract + direct extraction), 1,200+ documents/day at 95% extraction accuracy
- **Enterprise RAG chatbot** — hybrid retrieval + fine-tuned BERT/T5, RAGAS-evaluated before rollout, 35% relevance improvement

---

## Tech stack

**Languages & Frameworks:** Python · FastAPI · Flask · PyTorch

**LLM & Agentic:** LangChain · LangGraph · OpenAI SDK · A2A Protocol · MCP · Hugging Face

**Retrieval & Data:** Pinecone · FAISS · Redis · MySQL · SQL

**ML & Evaluation:** Scikit-learn · XGBoost · Statsmodels · MLflow · RAGAS

**Computer Vision:** YOLOv8 · ByteTrack · OpenCV

**Infra:** Docker · AWS (EC2, S3) · Asterisk ARI · Twilio · Ollama

---

## Currently exploring

- Fine-tuning and RLHF/DPO for post-training small language models
- Standardized multi-agent protocols (A2A, MCP) in production-style harnesses
- Agent reliability — guardrails, drift detection, and evaluation-before-trust practices

Feel free to reach out if you want to talk voice AI, agentic systems, or LLM evaluation.
