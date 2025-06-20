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


⸻

▶️ Usage

From your terminal, run:

./aletheai

The tool will:
	•	Process all PDFs in the input folder
	•	Extract and tag sentence-level content
	•	Generate statistics and semantic summaries

Outputs are saved in the locations specified in your config.

⸻

📂 Output
	•	*.csv: Tag and ESG dimension counts per report.
	•	*.json: GPT-based summaries of ESG themes and structural tags.
	•	runtime.yaml: Shows pipeline execution time.
	•	user_feedback.txt: Saved only if feedback is provided after a run.

⸻

💬 Feedback

After each run, you’ll be asked to leave feedback.
It is saved locally in user_feedback.txt in the working directory.

To share your thoughts, email this file to:
📩 info@aletheai.ch

⸻

❓ FAQ

Q: What platforms are supported?
A: Currently macOS (Apple Silicon). Windows/Linux coming soon.

Q: Do I need Python installed?
A: No. The tool runs as a standalone binary.

Q: I get “permission denied” — what now?
A: Make the binary executable:

chmod +x aletheai

Q: Where do I put my input files and config?
A: Match the structure described in your YAML config file.

Q: Where can I get an OpenAI API key?
A: Sign up at OpenAI

Q: Where is the output stored?
A: Output paths are defined in your config.yaml.

Q: How can I request a feature or report a bug?
A: Email your feedback file or contact us directly.

⸻

📬 Contact

Ana Dobson
📧 anbo.do@icloud.com
🌐 LinkedIn :https://www.linkedin.com/in/ana-dobson-a9295745/

⸻

📄 License

This software is provided in compiled form only.
You may use it for personal, educational, or evaluation purposes.
Commercial use, redistribution, reverse engineering, or modification is prohibited without written permission.

By using this software, you agree to these terms.
