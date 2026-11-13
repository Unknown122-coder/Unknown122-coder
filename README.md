# Akmal Khan

**ML and data engineer.** B.Tech Computer Science (Data Science), Manipal University Jaipur — class of 2027.

I build systems that show their work. The same idea runs through everything below: producing an answer is the easy half. The hard half is carrying the evidence that the answer is right — and returning *nothing* when the evidence isn't there.

[**Portfolio**](https://akmal-khan.vercel.app) · [**LinkedIn**](https://www.linkedin.com/in/akmal-khan-ba3945307) · 148akmalkhan@gmail.com

---

## Selected work

### [vexpath](https://github.com/Unknown122-coder/vexpath) — reachability-aware supply-chain security

[![PyPI](https://img.shields.io/pypi/v/vexpath)](https://pypi.org/project/vexpath/)
[![License](https://img.shields.io/badge/license-Apache--2.0-blue)](https://github.com/Unknown122-coder/vexpath/blob/main/LICENSE)

Your scanner reports 146 known vulnerabilities in your dependencies. Most of them sit in code your application never calls, and triaging which is which costs more than fixing them.

vexpath builds a call graph of your code *and* its installed dependencies, extracts the exact functions each advisory's fix commit touched, and clears a finding only when no path reaches them. Measured across five real repositories: **68 of 146 findings cleared as unreachable, none of them unsoundly.** Flask alone went from 38 findings to 10 worth reading.

Verdicts ship as signed [OpenVEX](https://openvex.dev) documents and in-toto attestations, gated in CI by a CEL policy engine. The hosted platform serves public report pages and README badges — server-rendered with **no JavaScript anywhere**, proven by a Playwright suite that drives the entire interface with scripting disabled.

→ `pip install vexpath` · live at [vexpath.fly.dev](https://vexpath.fly.dev) · 19,579 advisories and 27,877 vulnerable symbols across 805 packages

### [enterprise-multimodal-rag](https://github.com/Unknown122-coder/enterprise-multimodal-rag) — citations verified before they are shown

Document question answering where every claim names a document, page, chunk and quote that **provably appears in that chunk**. A claim whose citation cannot be verified against the source text is dropped rather than displayed.

Retrieval is hybrid dense + BM25, fused server-side and reranked by a cross-encoder, then *gated*: when the best evidence is too weak the service answers `not_found` without calling a language model at all. Ingestion runs offline — layout, reading order, table structure and OCR recovered by Docling into page-bounded chunks with bounding boxes.

→ Runs entirely on free tiers: Qdrant Cloud, Groq, Gemini, Colab, Hugging Face

### [credit-card-fraud-detection-system](https://github.com/Unknown122-coder/credit-card-fraud-detection-system) — the threshold is a business decision

Fraud is 0.172% of transactions, so a model that predicts "legitimate" every time scores 99.83% accuracy and catches nothing. Accuracy is the wrong objective, and so is any threshold picked off an ROC curve.

This one prices the errors instead: a false positive costs \$10 in review and friction, a false negative costs the transaction amount plus \$25. The operating threshold is chosen by minimising expected economic loss on a temporal validation split — a number in dollars, not a default of 0.5. Gradient-boosted ensembles with isotonic probability calibration, TreeSHAP for local and global explanations, served behind FastAPI.

---

## Toolkit

| | |
| :--- | :--- |
| **Machine learning** | scikit-learn · XGBoost · LightGBM · CatBoost · Optuna · MLflow · SHAP · imbalanced-learn |
| **LLM & retrieval** | Hybrid dense + BM25 · cross-encoder reranking · structured JSON output · Qdrant · pgvector · Groq · Gemini · LangChain |
| **Backend & data** | Python · SQL · FastAPI · SQLAlchemy · PostgreSQL · Pydantic · pandas · NumPy |
| **Platform** | Docker · GitHub Actions · Fly.io · Cloud Run · Vercel · Sigstore / in-toto · Playwright |
| **Frontend** | TypeScript · Astro · React |

---

## Elsewhere

**ML Intern** at Plasmid, Jaipur — May to July 2025.

Currently shipping vexpath. Next: a pharmacovigilance signal-detection explorer on FDA FAERS data, then a carbon-aware job scheduler that moves compute to the hours when the grid is cleanest.

<sub>Write-ups of each project live at <a href="https://akmal-khan.vercel.app">akmal-khan.vercel.app</a>.</sub>
