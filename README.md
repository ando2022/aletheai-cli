# aletheai-cli
# AletheAi CSR Evaluator

**AletheAi CSR Evaluator** is a command-line tool for automated analysis and summarization of Corporate Social Responsibility (CSR) reports.  
It extracts, tags, and summarizes ESG (Environmental, Social, Governance) dimensions, along with key structural features.

---

### 🏷️ Sentence Tag Definitions

Each sentence is evaluated using the following ESG-related tags:

| Tag            | Definition                                                                 | Identified By                                                                                         |
|----------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| `target`        | Identifies a specific goal, pledge, or objective.                           | Keywords such as *"target"*, *"aim to"*, *"commit to"*, or quantified aims like *"reduce by 30%"*.     |
| `time_bound`    | Indicates whether a time frame or deadline is mentioned.                    | References like *"by 2030"*, *"annually"*, *"Q1 2024"*, *"before the end of the year"*, etc.           |
| `numeric`       | Detects quantitative metrics or figures.                                    | Percentages, currency, emission units, counts of people or resources.                                 |
| `comparability` | Shows if the sentence allows comparison across time, standards, or baselines. | Phrases like *"compared to last year"*, *"vs. target"*, *"baseline"*, *"GHG protocol"*, *"YoY"*.      |
| `dimension`     | Classifies the sentence into ESG dimensions: Environmental (`E`), Social (`S`), Governance (`G`), or `None`. | Keyword matching against curated ESG vocabulary lists.                                                |

Tags are assigned using a rule-based method (regex + keyword matching), without machine learning or LLMs.

---

## 🚀 Features

- **Automated PDF-to-Insight Pipeline:** Converts CSR PDFs to text, extracts relevant sections, tags content, and generates ESG summaries.
- **ESG & Tag Summarization:** Summarizes not only ESG dimensions but also important tags like `target`, `numeric`, and `comparability`.
- **No Python Required:** Distributed as a standalone executable — no Python or dependencies needed.
- **OpenAI Integration:** Uses GPT-4 Turbo for high-quality semantic summaries (requires your own API key).
- **Configurable:** Input/output folders and limits set via a YAML config file.
- **Built-in Feedback Collection:** Option to provide feedback in-terminal after each run.

---

## 📦 Requirements

- **Operating System:** macOS (tested on 15.5, Apple Silicon).  
  _For Windows or Linux, please contact the developer._
- **OpenAI API Key:** Required for semantic summarization.
- **Input Files:** CSR reports in PDF format, and a YAML configuration file.

---

## 🛠️ Setup

1. **Download the Executable**

   - 👉 [Download AletheAi for macOS](https://github.com/ando2022/AletheAi/releases/download/v1.0.0/aletheai)
   - Unzip if necessary.

2. **Prepare Your Files**

   - Place the `aletheai` binary in your working directory.
   - Ensure your configuration file (e.g., `config.yaml`) and input PDFs are in the correct locations as specified in the config.

3. **Set Your OpenAI API Key**

   ```bash
   export OPENAI_API_KEY=sk-...
