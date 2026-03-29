# Synapse

An AI-powered weekly newsletter generator that curates and summarizes AI & ML news into a clean, shareable PDF. Built with a **LangGraph multi-agent pipeline**, it fetches news, generates summaries using an LLM, and compiles everything into a professionally formatted PDF with a branded cover page.

## Features

- Multi-agent LangGraph supervisor pipeline for orchestrating news collection and summarization
- Automated news fetching and LLM-based summarization
- PDF generation with custom branded cover and inner pages (ReportLab)
- Clean, readable format — cuts through noise to highlight what matters in AI each week
- Configurable output directory and date-based file naming

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core language |
| LangGraph | Multi-agent supervisor pipeline |
| LangChain / OpenAI | LLM-based summarization |
| ReportLab | PDF generation with custom layouts |
| NewsAPI / CSV | News data source |

## Project Structure

```
general-ai-synapse/
├── synapse/
│   ├── components/
│   │   ├── generate_pdf.py     # PDF generation with cover & inner pages
│   │   └── get_news.py         # News fetching component
│   ├── config/config.py        # Configuration (output dir, etc.)
│   ├── pipelines/supervisor.py # LangGraph supervisor pipeline
│   ├── prompts/summary_prompt.txt  # LLM prompt for summarization
│   └── utils/
│       ├── llm_utils.py        # LLM client utilities
│       └── logger.py           # Logging setup
├── artifacts/
│   ├── cover.png               # PDF cover page background
│   └── background.png          # PDF inner page background
├── data/                       # Generated PDFs organized by date
├── main.py                     # Entry point
├── news.csv                    # News data cache
└── pyproject.toml              # Project metadata
```

## Getting Started

### Prerequisites

- Python 3.10+
- API keys: OpenAI (or compatible LLM provider)

### Installation

```bash
git clone https://github.com/smunir25/general-ai-synapse.git
cd general-ai-synapse
pip install -r requirements.txt
```

Create a `.env` file:

```env
OPENAI_API_KEY=your_openai_key
```

### Run

```bash
python main.py
```

The generated PDF will be saved to `data/<DD-MM-YYYY>/Synapse <DD-MM-YYYY>.pdf`.

## Output

Each run produces a dated PDF newsletter with:
- A branded cover page with the publication date
- Individual inner pages per news article with title and AI-generated summary
- Clean typography and consistent layout throughout

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
