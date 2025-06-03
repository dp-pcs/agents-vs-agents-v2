# Agents-vs-Agents-v2
[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/dp-pcs/agents-vs-agents)

## Overview

Agents-vs-Agents-v2 is a benchmarking and evaluation suite for multi-agent orchestration frameworks using large language models (LLMs). It enables researchers and developers to compare the performance, output quality, and orchestration strategies of frameworks such as AutoGen, CrewAI, and LangGraph, leveraging LLMs from providers like OpenAI (GPT-4), Anthropic (Claude), and AWS Bedrock.

## Features
- **Benchmarking**: Run standardized tasks across multiple agent frameworks.
- **Evaluation**: Automated scoring and comparison using both OpenAI and Anthropic models.
- **Reporting**: Generate comprehensive markdown reports with performance metrics and qualitative assessments.
- **Extensible**: Easily add new frameworks, tasks, or evaluation metrics.

## Supported Frameworks & Models
- **Frameworks**: AutoGen, CrewAI, LangGraph
- **LLMs**: OpenAI GPT-4, Anthropic Claude, AWS Bedrock models

## Installation

### Python Environment
1. **Clone the repository:**
   ```bash
   git clone https://github.com/davidproctor/agents-vs-agents-v2.git
   cd agents-vs-agents-v2
   ```
2. **Create and activate a virtual environment (recommended):**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```
3. **Install Python dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

### Node.js (for visualization, if used)
If you plan to use Node-based visualization tools:
   ```bash
   npm install
   ```

### Environment Variables
Copy `.env.example` to `.env` and fill in your API keys for OpenAI, Anthropic, and AWS Bedrock as needed.

## Usage

### Running Benchmarks
Benchmarks are organized into two main pipelines:
- **Benchmark 1**: `src/runners/benchmark1/b1_run_all_benchmarks.py`
- **Benchmark 2**: `src/runners/benchmark2/b2_full_pipeline_run.py`

Example (run from project root):
```bash
python src/runners/benchmark1/b1_run_all_benchmarks.py
python src/runners/benchmark2/b2_full_pipeline_run.py
```

You can specify output directories and scoring options via command-line arguments. See the script source for more details.

### Scoring and Evaluation
To score outputs using LLMs:
```bash
python src/runners/scoring/standalone_scoring.py --file <output_markdown_file>
```

### Results and Reports
- All results and reports are saved in the `results/` directory.
- Markdown and HTML summaries are generated for easy sharing and analysis.

## Directory Structure
```
├── benchmark_all.py           # Legacy/combined benchmark script
├── requirements.txt           # Python dependencies
├── package.json               # Node dependencies (optional)
├── src/
│   ├── runners/               # Benchmark and scoring scripts
│   ├── frameworks/            # Implementations for each agent framework
│   ├── shared/                # Shared utilities and configs
│   └── tools/                 # Helper scripts (e.g., md_to_html)
├── results/                   # All generated outputs and reports
├── .env                       # API keys and environment config
└── ...
```

## Adding New Benchmarks or Frameworks
- Add your new agent framework logic under `src/frameworks/`.
- Register it in the relevant runner script under `src/runners/`.
- Update evaluation logic as needed in `src/shared/`.

## Contributing
Pull requests and issues are welcome! Please open an issue to discuss major changes.

## License
[MIT License](LICENSE)

---
For more information or help, click the DeepWiki badge at the top of this README.