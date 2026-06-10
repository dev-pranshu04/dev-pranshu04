# Developer Brand Strategy
## Pranshu Kumar · Complete Implementation Guide

---

## 1. Brand Positioning Statement

**The one-line identity:**
> *"ML engineer who builds AI for domains where being wrong has consequences — healthcare, materials science, and agentic systems. Every project is deployed."*

**Why this positioning wins:**
Most ML profiles say "I'm passionate about machine learning." This one says: I work on hard problems in high-stakes domains, I ship everything, and I can explain every design decision. That combination is genuinely rare at the early-career stage. It signals senior thinking in a junior candidate — which is exactly what a YC founder or engineering manager stops scrolling for.

---

## 2. GitHub Profile: Implementation Checklist

### Step 1 — Create the profile README repo
1. Go to github.com/new
2. Name the repo **exactly**: `dev-pranshu04`
3. Make it **Public**
4. Check "Add a README file"
5. Click Create repository
6. Delete the default README content
7. Paste the entire README from the attached file

### Step 2 — Pin repos in this exact order
The order signals priority to every visitor. Pin them in this sequence:
1. `resumeiq` — most impressive end-to-end system, most stars
2. `cardiorisk-ai` — high-stakes domain, strong AUC metrics, best documented
3. `nanostability-ai` — research credibility, full-stack deployment, live URL
4. `Sage_Research_Agent` — agentic AI, TypeScript, modern stack
5. `Stability-Prediction-of-Gold-Silver-Nanoclusters` — research depth
6. `Nordek_Internship_personal_project` — real-world internship signal

### Step 3 — GitHub profile bio (140 chars max)
```
ML Engineer · Physics-informed ML · Agentic AI · Clinical Decision Support · Everything deployed.
```

### Step 4 — GitHub profile links
- Website: your Streamlit app or portfolio URL
- LinkedIn: linkedin.com/in/dev-pranshu
- ORCID: orcid.org/0009-0006-4285-1817

### Step 5 — Add topics to every repo
These make repos discoverable via GitHub search:

**resumeiq:** `rag` `llm` `ollama` `langchain` `chromadb` `ats` `streamlit` `local-llm` `mistral` `sentence-transformers`

**cardiorisk-ai:** `healthcare-ai` `clinical-decision-support` `xgboost` `ensemble-learning` `calibration` `streamlit` `cardiovascular`

**nanostability-ai:** `physics-informed-ml` `nanoscience` `dft` `xgboost` `fastapi` `react` `materials-science` `machine-learning`

**Sage_Research_Agent:** `react-agent` `llm-agent` `groq` `nextjs` `typescript` `sse-streaming` `tavily` `autonomous-agent`

---

## 3. Banner Design Brief

**For Canva, Figma, or a designer:**

- **Dimensions:** 1500 × 500px (GitHub profile banner)
- **Background:** Deep space gradient — `#0a0a0f` (far left) → `#1a0533` (center-left) → `#2d1b69` (center) → `#0a0a0f` (far right). No noise texture, no gradients that look cheap.
- **Typography:** Name "PRANSHU KUMAR" in a clean geometric sans-serif (Space Grotesk, Inter, or Syne). 72px, weight 600, color `#E8D5FF`. Left-aligned, vertically centered.
- **Subtitle line:** "ML Engineer · AI for High-Stakes Domains" — 22px, `#9D7FD4`, same left alignment, 12px below name.
- **Right side element:** A subtle, elegant illustration — abstract node-graph lines suggesting a neural network or molecular structure. Low opacity (15–20%), color `#7C3AED`. This is *decoration*, not the focus.
- **What to absolutely avoid:** Stock photos of brains, generic "AI" imagery, circuit board textures, neon glow effects, robotic hands, any cliché tech iconography.

**Simpler alternative (no designer needed):**
Use capsule-render with these parameters — already embedded in the README. It renders clean purple-dark gradients with your name and tagline automatically.

---

## 4. Profile Photo Recommendations

**What recruiters and founders respond to:**
- Plain, slightly muted background (dark grey, off-white, or deep blue — not a wall or a busy scene)
- Visible from the shoulders up
- Direct eye contact with camera
- Neutral-to-slight smile — approachable, not stiff
- Professional but not corporate. A clean t-shirt or casual collared shirt works better than a suit for ML/AI roles.
- **Lighting:** Natural light from a window beside you (not behind you). Avoid overhead fluorescent.

**What kills first impressions:**
- Selfie angle (camera below eye level, distorted)
- Group photos cropped to just you
- Sunglasses, heavy filters, vacation shots
- Blurry or low resolution
- No photo at all (this costs you more than a bad photo)

---

## 5. LinkedIn Optimization

### Headline (220 chars max — use all of it)
```
ML Engineer · Agentic AI | Clinical Decision Support | Physics-Informed ML | Building AI that ships and earns trust in high-stakes domains
```

**Why this headline wins:** Most ML developers write "Machine Learning Engineer | Python | TensorFlow." That's a job title, not a brand. This headline tells a recruiter three things in one sentence: what you build, where you apply it, and what you believe about it.

### About Section (full copy — ready to paste)

```
I build machine learning systems for domains where the cost of being wrong is high.

That constraint changes everything about how you design. In clinical AI, you optimize 
for calibration alongside accuracy — because a model that says 73% should mean 73%, 
and a clinician needs to know how much to trust the output, not just whether it's 
usually right. In scientific ML, you encode domain knowledge as model priors — 
because a gradient boosting model that understands HOMO-LUMO gap is more useful 
than one that treats every feature as equivalent noise. In agentic AI, you build 
judgment, not just capability — because an agent that searches indiscriminately is 
slower and worse than one that knows when to stop.

Selected work:

→ ResumeIQ — End-to-end local LLM pipeline for ATS analysis. Runs Mistral-7B via 
  Ollama, scores resumes across 8 dimensions, rewrites bullets in STAR format, 
  exports improved .docx. Zero cloud cost, zero data exposure. Full CI/CD to GHCR.

→ CardioRisk AI — Clinical decision support for cardiovascular risk. XGBoost + 
  Logistic Regression ensemble trained on 920 patients across 4 institutions. 
  0.910 AUC-ROC. Risk thresholds calibrated for patient safety, not F1 optimization.

→ NanoStability AI — Physics-informed ML for Au/Ag nanocluster stability. 
  Built at NSUT Computational Chemistry Lab. 85% accuracy, 0.912 ROC-AUC. 
  XGBoost + SVM + MLP ensemble on 11 DFT-derived features. FastAPI + React, 
  live at nanostability-ai.vercel.app.

→ Sage Research Agent — ReAct-loop AI agent with SSE streaming, live web search, 
  and autonomous planning. Built on Next.js 14, Groq, Tavily. Fully free to run.

Every project is deployed and publicly accessible.

Open to ML engineering roles, research collaborations in scientific or clinical AI, 
and founding team conversations at AI-for-science companies.

GitHub: github.com/dev-pranshu04
ORCID: orcid.org/0009-0006-4285-1817
```

### Featured Section (3 items, in this order)
1. **ResumeIQ live app** — resumeiq-pk04.streamlit.app (most relatable, highest click rate)
2. **NanoStability AI live app** — nanostability-ai.vercel.app (research credibility signal)
3. **GitHub profile** — github.com/dev-pranshu04 (drives profile traffic)

### Experience Section — How to write each internship entry

**Nordek Blockchain (Fintech Internship)**
```
Built a production Streamlit dashboard combining LSTM deep learning and XGBoost 
gradient boosting for NRK cryptocurrency price forecasting. Designed the 
hybrid architecture to capture temporal sequence patterns (LSTM) and feature 
interaction signals (gradient boosting) simultaneously — neither model alone 
handled both. Dashboard deployed and used by the team throughout the internship.
```

**NSUT Computational Chemistry Lab**
```
Applied physics-informed machine learning to Au/Ag nanocluster stability 
prediction as part of an academic research internship. Built an XGBoost + SVM + 
MLP ensemble using 11 DFT-derived quantum chemistry features (HOMO-LUMO gap, 
formation energy, binding energy). Achieved 85% accuracy and 0.912 ROC-AUC on 
200 nanocluster samples. Deployed full-stack: FastAPI backend + React frontend, 
live at nanostability-ai.vercel.app.
```

---

## 6. GitHub SEO — Search Discoverability

GitHub search ranks profiles and repositories by: username keywords, bio text, repository topics, repository description text, and README content.

**Username:** `dev-pranshu04` — already has "dev" in it, which is a search signal.

**Bio:** Add `ml-engineer`, `agentic-ai`, `healthcare-ai`, `physics-informed-ml` as natural phrases — these appear in search results.

**Repository descriptions** (the one-line description under each repo name) — update these to include high-value search keywords:

- resumeiq: `"Offline ATS intelligence. Local LLM pipeline (Mistral-7B + LangChain + ChromaDB) for resume scoring, gap analysis, and STAR rewriting. Zero API cost."`
- cardiorisk-ai: `"Clinical decision support for cardiovascular risk. XGBoost + LR ensemble, 0.910 AUC-ROC, 920 patients. Calibrated risk tiers for clinical use."`
- nanostability-ai: `"Physics-informed ML for Au/Ag nanocluster stability. XGBoost + SVM + MLP ensemble, 85% accuracy. FastAPI + React. NSUT Comp. Chemistry Lab."`
- Sage_Research_Agent: `"Autonomous ReAct-loop AI agent. Groq + Llama 3.3 70B + Tavily. SSE streaming. Next.js 14 + TypeScript. Fully free."`

---

## 7. The One Missing Piece: Personal Portfolio Site

A portfolio site at `pranshu.dev` or `pranshukumar.com` or even `dev-pranshu.vercel.app` would complete the professional picture and serve as a canonical URL you control.

**Minimum viable version (one page, 4 hours of work):**
- Hero: name, title, one-line positioning statement
- Projects: the same 4 featured projects with live links
- Contact: LinkedIn + GitHub + email
- Deploy to Vercel (free)

This URL then goes in your GitHub bio, LinkedIn header, email signature, and every README. It becomes the single hub that all other surfaces point to.

---

## 8. The 10-Minute Setup (Do This Today)

1. Create `dev-pranshu04/dev-pranshu04` repo → paste README
2. Update GitHub bio to: `ML Engineer · Physics-informed ML · Agentic AI · Clinical Decision Support · Everything deployed.`
3. Pin the 6 repos in the order listed above
4. Add topics to all 4 main repos
5. Update LinkedIn headline to the copy above
6. Add 3 Featured items on LinkedIn
7. Update each repo description with the SEO copy

Total time: ~45 minutes. Impact: permanent.

---

*Every recommendation in this document is specific to Pranshu's actual work — not a template.*
