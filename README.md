<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0a0f,30:1a0533,60:2d1b69,100:0a0a0f&height=220&section=header&text=Pranshu%20Kumar&fontSize=56&fontColor=E8D5FF&fontAlignY=40&fontAlign=50&desc=I%20build%20AI%20that%20earns%20trust%20in%20domains%20where%20being%20wrong%20has%20consequences&descAlignY=62&descSize=15&descColor=9D7FD4&animation=fadeIn" width="100%"/>

</div>

<br/>

<div align="center">
<a href="https://www.linkedin.com/in/dev-pranshu/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" height="26"/></a>&nbsp;
<a href="https://orcid.org/0009-0006-4285-1817"><img src="https://img.shields.io/badge/ORCID-A6CE39?style=flat-square&logo=orcid&logoColor=white" height="26"/></a>&nbsp;
<a href="https://resumeiq-pk04.streamlit.app/"><img src="https://img.shields.io/badge/ResumeIQ_Live-FF4B4B?style=flat-square&logo=streamlit&logoColor=white" height="26"/></a>&nbsp;
<a href="https://sage-kappa-five.vercel.app"><img src="https://img.shields.io/badge/Sage_Agent_Live-000000?style=flat-square&logo=vercel&logoColor=white" height="26"/></a>&nbsp;
<a href="https://nanostability-ai.vercel.app"><img src="https://img.shields.io/badge/NanoStability_Live-7C3AED?style=flat-square&logo=vercel&logoColor=white" height="26"/></a>
</div>

<br/>

---

## The thread

Most ML developers pick a lane — NLP, or CV, or tabular data — and stay there. I went sideways.

I've applied ML to cardiovascular risk (920 patients, 4 clinical sites), nanomaterial stability (DFT-informed features, Au/Ag clusters), cryptocurrency forecasting (LSTM + XGBoost hybrid), and autonomous AI agents with real-time web synthesis. Not as an exercise in breadth. As a consequence of asking one question repeatedly: *what does this domain actually need from a model that most practitioners miss?*

In cardiology, it's calibration — a model that says 73% should mean 73%, because the cost of overconfidence is a missed referral. In nanoscience, it's physics-informed features — HOMO-LUMO gap and formation energy aren't arbitrary inputs, they're the quantum-mechanical fingerprint of whether a cluster holds together. In agentic AI, it's judgment — the agent needs to decide *when* to search, not just *how*, because indiscriminate tool use is noise.

Every project in this profile is a deployed product with a live URL, a documented architecture, and design decisions I can defend under questioning. I write READMEs the way I write code: architecture-first, with every tradeoff named.

**Now:** Deepening expertise in agentic systems, LLM orchestration, and local-first inference. Building toward AI infrastructure for high-stakes domains where explainability is a hard requirement, not a talking point.

---

## What I'm building right now

| | Project | Status |
|---|---|---|
| 🔬 | Physics-informed ML for scientific property prediction | Active |
| 🤖 | Multi-step agentic pipelines with structured tool use | Active |
| 🏥 | Clinical AI with calibrated uncertainty and risk tiers | Deployed |
| 🔒 | Local-first LLM infrastructure (zero cloud, zero cost, zero data exposure) | Deployed |
| 📄 | End-to-end document intelligence with RAG and semantic reranking | Deployed |

---

## The work

### ResumeIQ — Offline ATS Intelligence Platform

> *75% of resumes are rejected before a human reads them. Not because the candidate is underqualified. Because the ATS parser doesn't recognize their keywords. ResumeIQ fixes that — entirely on your machine.*

The conventional tools for this problem use cloud LLM APIs. They're expensive, they expose your resume to third-party servers, and they go down. I built the opposite: a fully local pipeline running Mistral-7B via Ollama that scores a resume across 8 dimensions, rewrites every bullet point in STAR format, simulates the ATS parser's view vs. the recruiter's view, and exports a corrected `.docx` — at zero API cost, with the model weights running on your CPU.

The architecture decision that most people miss: scoring is 65% LLM semantic judgment blended with 35% ChromaDB cosine similarity. The LLM alone drifts on long documents — chunking (300 tokens, 40-token overlap via LangChain) keeps semantic context tight, and the vector similarity score anchors the LLM's judgment against an objective similarity measure. Neither alone is as reliable as both together.

Ships with a full CI/CD pipeline: GitHub Actions → ruff lint → pytest → Docker image build → push to GHCR → GitHub release tag.

```
Tech: Python · Ollama · Mistral-7B · LangChain · ChromaDB · SentenceTransformers
      all-MiniLM-L6-v2 · Streamlit · python-docx · Docker · GitHub Actions
```

[![Repo](https://img.shields.io/badge/Code-dev--pranshu04/resumeiq-181717?style=flat-square&logo=github)](https://github.com/dev-pranshu04/resumeiq)
[![Live](https://img.shields.io/badge/Live_App-resumeiq--pk04.streamlit.app-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)](https://resumeiq-pk04.streamlit.app/)
[![Stars](https://img.shields.io/github/stars/dev-pranshu04/resumeiq?style=flat-square&color=FFD700&label=⭐)](https://github.com/dev-pranshu04/resumeiq/stargazers)

---

### CardioRisk AI — Clinical Decision Support

> *Cardiovascular disease is the leading cause of death globally. A clinician with 13 routine measurements and 90 seconds should be able to get a calibrated risk score. This does that.*

The design philosophy here is deliberately different from most healthcare ML projects. Most optimize for AUC. I optimized for clinical usefulness — which meant making three choices that aren't in any textbook.

First, the risk thresholds (0.30 / 0.60) are not split evenly. They're set to minimize false negatives in the HIGH tier, because in cardiology, the cost of sending a healthy patient for more tests is far lower than the cost of telling a sick patient they're fine.

Second, median imputation over SMOTE for class imbalance. SMOTE generates synthetic patients that don't exist. Median imputation makes a conservative assumption about real patients. In a medical dataset, synthetic data artifacts are a liability.

Third, the 65/35 XGBoost-to-LR ensemble weight. Logistic Regression produces well-calibrated probabilities on linearly separable feature subspaces. Including it at 35% weight smooths XGBoost's overconfident edge-case predictions — the exact cases where you most need calibration to hold.

Result: 0.910 AUC-ROC, 0.900 five-fold CV AUC (low variance), trained on 920 patients across four clinical institutions (Cleveland, Hungary, Switzerland, VA Long Beach) — geographic diversity that actively reduces single-centre bias.

```
Tech: Python · XGBoost · scikit-learn · Logistic Regression · Streamlit
      Pandas · Matplotlib · UCI Heart Disease Dataset (920 patients, 4 sites)
```

[![Repo](https://img.shields.io/badge/Code-dev--pranshu04/cardiorisk--ai-181717?style=flat-square&logo=github)](https://github.com/dev-pranshu04/cardiorisk-ai)
[![Live](https://img.shields.io/badge/Live_App-cardiorisk--ai--pk04.streamlit.app-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)](https://cardiorisk-ai-pk04.streamlit.app/)
[![AUC](https://img.shields.io/badge/AUC--ROC-0.910-22C55E?style=flat-square)](https://github.com/dev-pranshu04/cardiorisk-ai)
[![Stars](https://img.shields.io/github/stars/dev-pranshu04/cardiorisk-ai?style=flat-square&color=FFD700&label=⭐)](https://github.com/dev-pranshu04/cardiorisk-ai/stargazers)

---

### NanoStability AI — Physics-Informed ML for Nanoscience

> *DFT simulations take hours per cluster. Screening 10,000 candidates is computationally impossible. ML that speaks the language of quantum chemistry can change that.*

Built during my internship at NSUT Computational Chemistry Lab (May–Aug 2025). The core insight: if you give a gradient boosting model the same features a computational chemist uses to reason about stability — HOMO-LUMO gap, formation energy, binding energy, coordination number — it can learn the physical intuition behind why some clusters hold together and others don't.

The ensemble: XGBoost (300 trees) + SVM (RBF kernel) + MLP (64-32-16). Each model captures a different aspect of the structure-stability relationship. XGBoost handles nonlinear interactions between quantum features. SVM with RBF kernel finds the stability boundary in high-dimensional feature space. MLP captures learned representations that neither tree nor kernel method can.

**85% accuracy, 0.912 ROC-AUC** on 200 Au/Ag nanoclusters (n = 3–20 atoms, 11 DFT-derived features).

Full-stack deployment: FastAPI backend (pre-trained `.joblib`, instant load) + React frontend. Auto-deploys via `render.yaml` + `vercel.json` — push to main, both services redeploy in two minutes.

```
Tech: Python · XGBoost · SVM · MLP · FastAPI · React · scikit-learn
      joblib · Render · Vercel · DFT-derived features
```

[![Repo](https://img.shields.io/badge/Code-dev--pranshu04/nanostability--ai-181717?style=flat-square&logo=github)](https://github.com/dev-pranshu04/nanostability-ai)
[![Live](https://img.shields.io/badge/Live_App-nanostability--ai.vercel.app-7C3AED?style=flat-square&logo=vercel&logoColor=white)](https://nanostability-ai.vercel.app)
[![Accuracy](https://img.shields.io/badge/Accuracy-85%25-22C55E?style=flat-square)](https://github.com/dev-pranshu04/nanostability-ai)

---

### Sage Research Agent — ReAct-Loop AI Agent

> *You ask a question. The agent plans, searches the web up to five times, and returns a cited, structured report. Streaming. Real-time. Free.*

The key architecture decision is where the intelligence lives. A naive implementation pre-writes the search queries. Sage uses a ReAct loop — the LLM reasons about whether it has enough information to answer *before* deciding whether to search again. Tool calling is judgment-driven, not scripted. This is the difference between an LLM with a search button and an actual reasoning agent.

Server-Sent Events stream each reasoning step to the frontend as it happens — you watch the agent think, not a spinner. Built on Next.js 14 App Router with full TypeScript throughout, powered by Groq's Llama 3.3 70B at free-tier speeds (~14,400 req/day).

Total infrastructure cost: $0.

```
Tech: Next.js 14 · TypeScript · Groq · Llama 3.3 70B · Tavily API
      SSE Streaming · ReAct Architecture · Vercel
```

[![Repo](https://img.shields.io/badge/Code-dev--pranshu04/Sage_Research_Agent-181717?style=flat-square&logo=github)](https://github.com/dev-pranshu04/Sage_Research_Agent)
[![Live](https://img.shields.io/badge/Live_App-sage--kappa--five.vercel.app-000000?style=flat-square&logo=vercel&logoColor=white)](https://sage-kappa-five.vercel.app)

---

### Nordek Crypto Forecaster — Deep Learning + Gradient Boosting Hybrid

> *A production-grade Streamlit dashboard combining LSTM sequence modeling with XGBoost feature interactions for NRK cryptocurrency price prediction.*

Built during a fintech internship at Nordek Blockchain. The architectural thesis: LSTM captures temporal patterns (momentum, trend reversals, volatility regimes). XGBoost captures feature interactions (volume × price spread, RSI × MACD divergence). Neither model alone handles both. The dashboard presents both outputs alongside ensemble predictions with confidence intervals.

```
Tech: Python · LSTM · XGBoost · Streamlit · Pandas · deep learning
```

[![Repo](https://img.shields.io/badge/Code-dev--pranshu04/Nordek_Internship--project-181717?style=flat-square&logo=github)](https://github.com/dev-pranshu04/Nordek_Internship_personal_project)

---

## Stack

<div align="center">

| Layer | Technologies |
|---|---|
| **Primary Languages** | Python · TypeScript · JavaScript · SQL |
| **ML / AI Core** | XGBoost · scikit-learn · PyTorch · SentenceTransformers · LangChain |
| **LLMs & Inference** | Ollama · Mistral-7B · Groq · Llama 3.3 70B · ChromaDB |
| **Full-Stack** | Next.js 14 · React · FastAPI · Streamlit · Tailwind CSS |
| **Data** | Pandas · NumPy · Plotly · Matplotlib · pdfplumber |
| **DevOps** | Docker · GitHub Actions · Ruff · pytest · GHCR |
| **Cloud & Deploy** | Vercel · Render · Streamlit Cloud |
| **Research** | DFT-derived features · HOMO-LUMO gap modeling · RAG · SSE streaming |

</div>

---

## Metrics

<div align="center">

<img height="175em" src="https://github-readme-stats.vercel.app/api?username=dev-pranshu04&show_icons=true&theme=tokyonight&hide_border=true&count_private=true&include_all_commits=true&rank_icon=github&title_color=9D7FD4&icon_color=9D7FD4&text_color=c9d1d9&bg_color=0d1117"/>
<img height="175em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=dev-pranshu04&layout=compact&theme=tokyonight&hide_border=true&langs_count=8&title_color=9D7FD4&text_color=c9d1d9&bg_color=0d1117"/>

</div>

<div align="center">
<img src="https://github-readme-streak-stats.herokuapp.com?user=dev-pranshu04&theme=tokyonight&hide_border=true&ring=9D7FD4&fire=9D7FD4&currStreakLabel=9D7FD4" width="55%"/>
</div>

<div align="center">
<img src="https://github-readme-activity-graph.vercel.app/graph?username=dev-pranshu04&bg_color=0d1117&color=9D7FD4&line=9D7FD4&point=E8D5FF&area=true&area_color=2d1b69&hide_border=true" width="95%"/>
</div>

---

## Credentials

| | |
|---|---|
| **ORCID** | [0009-0006-4285-1817](https://orcid.org/0009-0006-4285-1817) — formal research identity across published and academic work |
| **NSUT Comp. Chemistry Lab** | ML research internship, May–Aug 2025 — physics-informed ML on real DFT datasets |
| **Nordek Blockchain** | Fintech internship — production forecasting dashboard in live use |
| **GitHub Actions CI/CD** | ResumeIQ ships with a full pipeline: lint → test → Docker build → GHCR push → tagged release |

---

## How I think

**On model selection:** The right model for a problem is the one that encodes what you already know about the domain — not the one that scores highest on the leaderboard. XGBoost for cardiology because nonlinear feature interactions are real. Physics-informed features for nanoscience because quantum chemistry is real. Local Mistral for ATS scoring because privacy is real.

**On calibration vs. accuracy:** In high-stakes domains, a model that says 73% should mean 73%. Accuracy tells you how often the model is right. Calibration tells you how much to trust it when it's uncertain. I optimize for both, but calibration is the one that determines whether a clinician can actually use the output.

**On deployment:** A model that doesn't ship doesn't exist. Every project in this profile has a live URL. Not because deployment is glamorous — it's tedious — but because the only way to know if something actually works is to run it in the real world.

**On explainability:** I don't treat explainability as a regulatory checkbox. I treat it as a design constraint that makes better models. If you can't explain why the XGBoost model flagged fluoroscopy vessel count as the top predictor, you can't validate that the model learned cardiology instead of learning dataset artifacts.

---

## Learning trajectory

```
Currently    ──▶  Agentic AI systems · multi-step planning · structured tool use
Next         ──▶  LLM fine-tuning with LoRA/QLoRA on domain-specific corpora
Following    ──▶  Distributed training · PyTorch DDP · gradient checkpointing
Research     ──▶  Physics-informed neural networks · graph NNs for molecular property prediction
Always       ──▶  MLOps · model versioning · production drift detection
```

---

## Open to

- ML engineering roles at companies where the model actually ships to users
- Research collaborations in scientific ML, clinical AI, or agentic systems
- Founding team conversations at AI-for-science or developer-tools startups
- Anyone building in domains where being wrong has consequences

---

<div align="center">

**Pranshu Kumar**

[linkedin.com/in/dev-pranshu](https://www.linkedin.com/in/dev-pranshu/) · [orcid.org/0009-0006-4285-1817](https://orcid.org/0009-0006-4285-1817)

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0a0f,30:1a0533,60:2d1b69,100:0a0a0f&height=100&section=footer&fontColor=9D7FD4" width="100%"/>

</div>
