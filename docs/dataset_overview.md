**FinGuard-SDG Benchmark Dataset — Overview

**1. Purpose of the Dataset**The **FinGuard-SDG Benchmark v1.0** is a curated dataset designed to evaluate **routing and orchestration mechanisms** in financial AI systems. 

Unlike traditional QA datasets, this benchmark is **not intended for answer generation**, but for **intent classification and routing** across heterogeneous financial tasks, including:  

<pre>
  * numerical finance problems,
  * conceptual finance questions,
  * ESG and sustainability analysis,
  * advisory and scenario-based investor guidance.
</pre>

The dataset supports research at the **intersection of financial technology and sustainability**, in alignment with the **United Nations Sustainable Development Goals (SDGs)**.

**2. Dataset Composition
**
The dataset consists of **1,160 finance-domain questions**, each labeled with a high-level intent category.

**Category Distribution**

| Category     | Description                                                           | Count     |
| ------------ | --------------------------------------------------------------------- | --------- |
| Quantitative | Time value of money, valuation, portfolios, risk metrics, derivatives |  440      |
| Conceptual   | Financial theory, markets, risk, regulation, behavioral finance       |  240      |
| ESG          | Environmental, Social, and Governance topics aligned with SDGs        |  220      |
| Advisory     | Investor profiling, asset allocation, scenario-based guidance         |  260      |
| **Total**    |                                                                     |**1,160**  |

**3. Schema**
Each record in FinGuard_SDG_Benchmark_v1.0.csv follows the schema below:
| Field           | Description                                                        |
| --------------- | ------------------------------------------------------------------ |
| `id`            | Unique, stable question identifier                                 |
| `category`      | One of `{quantitative, conceptual, esg, advisory}`                 |
| `subcategory`   | Fine-grained topic within each category                            |
| `question_text` | Natural-language financial question                                |
| `answer_text`   | Reference answer (used for context, not generation)                |
| `difficulty`    | Difficulty level: 1 (easy), 2 (medium), 3 (hard)                   |
| `source`        | Question origin: `template`, `literature-inspired`, or `synthetic` |

**4. Dataset Construction (Summary)**
The dataset was constructed using a block-wise, controlled generation strategy:

<pre>
  * Quantitative questions were created using structured financial templates (e.g., TVM, bond valuation, portfolio math) to ensure numerical correctness.
  * Conceptual questions were literature-inspired, reflecting standard finance curricula (e.g., CFA-level topics).
  * ESG questions were designed to reflect SDG-aligned financial analysis, including climate risk, social inclusion, governance practices, and disclosure.
  * Advisory questions were framed as scenario-based investor guidance, emphasizing suitability, trade-offs, and responsible investment considerations.
</pre>
A full description of the dataset construction methodology, quality assurance process, and SDG alignment is provided in the accompanying research paper.

**5. Quality Assurance**

Before use in experiments, the dataset underwent systematic quality checks, including:
<pre>
  * schema validation,
  * duplicate ID detection,
  * category and subcategory balance analysis,
  * difficulty distribution checks,
  * verification of missing or malformed fields.
</pre>
The final dataset contains:
<pre>
  * 1,160 unique IDs,
  * no missing fields,
  * balanced difficulty and category distributions suitable for supervised routing experiments.
</pre>


