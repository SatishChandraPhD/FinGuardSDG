# FinGuardSDG
**FinGuard-SDG
**
**FinGuard-SDG** is a reproducible research codebase accompanying the paper:

**FinGuard-SDG: A Hybrid Multi-Agent Routing Architecture for Sustainable Financial Analytics**

The repository provides:
  * a curated multi-task financial benchmark dataset aligned with the **UN Sustainable Development Goals (SDGs)**,
  * and a **hybrid routing architecture** for financial AI systems that combines
    **keyword heuristics, encoder-based semantic routing, and selective LLM fallback**.

**🔍 Motivation**

Financial AI systems increasingly need to handle heterogeneous queries, including:
  * quantitative financial calculations,
  * conceptual finance questions,
  * ESG and sustainability analysis,
  * and advisory-style investor guidance.

Single-stage routing approaches struggle with **implicit reasoning**, especially for:
  * numerically implicit questions,
  * ESG–advisory overlap,
  * and ambiguous financial intent.

This work proposes and evaluates a **hybrid routing architecture** that is:
 * accurate,
 * computationally efficient,
 * and aligned with sustainable finance objectives.

**📊 Dataset: FinGuard-SDG Benchmark v1.0
**
**FinGuard_SDG_Benchmark_v1.0.csv** contains **1,160 finance-domain questions** across four categories:
| Category     | Description                                                      |
| ------------ | ---------------------------------------------------------------- |
| Quantitative | Numerical finance (TVM, bonds, portfolios, derivatives)          |
| Conceptual   | Financial theory, markets, risk, and regulation                  |
| ESG          | Environmental, Social, and Governance analysis aligned with SDGs |
| Advisory     | Investor profiling, allocation, scenario-based guidance          |



**Dataset highlights**
  * Designed for **routing, not QA generation**
  * Difficulty-balanced (easy / medium / hard)
  * SDG-aligned ESG coverage  
  * Suitable for **multi-agent financial systems
**
**Full dataset construction methodology is described in the paper.
**
A concise dataset overview is provided in docs/dataset_overview.md.

**📁 Repository Structure**
<pre>
 FinGuardSDG/
├── data/
│   ├── FinGuard_SDG_Benchmark_v1.0.csv
│   ├── train.csv
│   ├── val.csv
│   └── test.csv
│
├── data_processing/
│   ├── 01_data_QA.ipynb
│   └── 02_data_split_and_export.ipynb
│
├── notebooks/
│   ├── 03_keyword_router.ipynb
│   ├── 04_encoder_router.ipynb
│   ├── 05_hybrid_router.ipynb
│   └── 06_llm_fallback_router.ipynb
│
├── models/
│   └── .gitkeep
│
├── results/
│   ├── keyword/
│   ├── encoder/
│   ├── hybrid/
│   └── llm/
│
├── docs/
│   └── dataset_overview.md
│
├── requirements.txt
├── README.md
└── LICENSE
</pre>

**⚙️ Experimental Pipeline**

All experiments were implemented as **Jupyter notebooks** and executed in a **Google Colab environment**.

**Pipeline order**

 1. Data QA & Validation
      <pre>01_data_QA.ipynb</pre>
2.  Deterministic Train/Val/Test Split + JSONL export
      <pre>02_data_split_and_export.ipynb</pre>
3.  Keyword-only Router (baseline)
      <pre>03_keyword_router.ipynb</pre>
4.  Encoder Router (MiniLM)
      <pre>04_encoder_router.ipynb</pre>
5.  Hybrid Router (Keyword → Encoder)
      <pre>05_hybrid_router.ipynb</pre>
6.  LLM Fallback Router (Llama-2)
      <pre>06_llm_fallback_router.ipynb</pre>

All experiments use **fixed random seeds** to ensure reproducibility.

**🤖 Routing Architectures Evaluated** All reported metrics and confidence intervals are computed using ”07_Unified_Evaluation.ipynb"
* Keyword Router<pre>Lightweight lexical baseline. </pre>
* Encoder Router (MiniLM)<pre>Sentence-embedding-based semantic classification.</pre>
* Hybrid Router (Keyword → Encoder)<pre>Keyword routing for explicit numericals, encoder fallback for ambiguity.</pre>
* Hybrid + LLM Fallback (Llama-2)<pre>LLM invoked only for low-confidence cases.</pre>

**📈 Reproducibility**
 * Deterministic dataset splits
 * Fixed random seeds
 * Greedy decoding for LLM routing
 * Models saved locally by the user (not distributed)
   
Trained models are **not included** in the repository.
Users may save models locally or mount Google Drive when using Colab.

**🔐 Model Storage (Colab Example)**
<pre>from google.colab import drive
drive.mount('/content/drive')

MODEL_DIR = "/content/drive/MyDrive/FinGuard/models/"
</pre>

Models are saved and loaded relative to MODEL_DIR.

**📄 Related Publication**

This repository accompanies:
Journal manuscript submitted to FinTech and Sustainable Innovation</pre>
A DOI / preprint link will be added upon publication.

**📜 License**

This repository is released under the MIT License.
The dataset is intended for research and educational use.

**📬 Contact****

**Satish Chandra**

PhD Researcher

GitHub: https://github.com/SatishChandraPhD
