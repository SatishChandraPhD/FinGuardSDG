# FinGuardSDG
**FinGuard-SDG
**
**FinGuard-SDG** is a reproducible research codebase accompanying the paper:

**FinGuard-SDG: A Hybrid Multi-Agent Routing Architecture for Sustainable Financial Analytics**
(IEEE CSCloud 2025; extended journal version under preparation)

The repository provides:

  * a curated multi-task financial benchmark dataset aligned with the UN Sustainable Development Goals (SDGs),
  
  * and a hybrid routing architecture for financial AI systems that combines
  keyword heuristics, encoder-based semantic routing, and selective LLM fallback.

Motivation

Financial AI systems increasingly need to handle heterogeneous queries, including:
  quantitative financial calculations,
  conceptual finance questions,
  ESG and sustainability analysis,
  and advisory-style investor guidance.

Single-stage routing approaches struggle with implicit reasoning, especially for:
  numerically implicit questions,
  ESG–advisory overlap,
  and ambiguous financial intent.

This work proposes and evaluates a hybrid routing architecture that is:

accurate,
computationally efficient,
Motivation

Financial AI systems increasingly need to handle heterogeneous queries, including:

quantitative financial calculations,

conceptual finance questions,

ESG and sustainability analysis,

and advisory-style investor guidance.

Single-stage routing approaches struggle with implicit reasoning, especially for:

numerically implicit questions,

ESG–advisory overlap,

and ambiguous financial intent.

This work proposes and evaluates a hybrid routing architecture that is:
  accurate,
  computationally efficient,
  and aligned with sustainable finance objectives.
  
**Dataset: FinGuard-SDG Benchmark v1.0
**
FinGuard_SDG_Benchmark_v1.0.csv contains 1,160 finance-domain questions across four categories:
| Category     | Description                                                      |
| ------------ | ---------------------------------------------------------------- |
| Quantitative | Numerical finance (TVM, bonds, portfolios, derivatives)          |
| Conceptual   | Financial theory, markets, risk, and regulation                  |
| ESG          | Environmental, Social, and Governance analysis aligned with SDGs |
| Advisory     | Investor profiling, allocation, scenario-based guidance          |



**Dataset highlights**

  Designed for routing, not QA generation
  Difficulty-balanced (easy / medium / hard)
  SDG-aligned ESG coverage  
  Suitable for multi-agent financial systems

**Full dataset construction methodology is described in the paper.
**
A concise dataset overview is provided in docs/dataset_overview.md.










