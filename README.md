# ambitus-intelligence 🔍
<!-- Reframe below line as the application is TUI native now. -->
<!-- **Part of the [ambitus Intelligence](https://github.com/ambitus-intelligence) Ecosystem** -->
Ambitus Intelligence is a TUI‑first Python package and multi‑agent market research engine that orchestrates validated data collection, analysis, and report synthesis into citation‑rich PDF reports.


This repository contains AI/ML models, experiments, and tools powering **ambitus Intelligence**'s market research automation platform.  
All exploratory work, prototypes, and notebooks are organized under `/notebooks`.

---

## 🚀 Overview

`ambitus-ai-models` is the core engine behind Ambitus Intelligence’s automated market research platform. It provides:

- **Orchestrated Multi‑Agent Workflows**  
  A centralized Orchestrator sequences specialized AI agents, handles error‑flows, and manages user hand‑offs.

- **FastMCP Tool Server**  
  `ambitus-tools-mcp`—a MCP server, backed by FastMCP—hosts all external utilities (scrapers, API clients, validators) and the CitationAgent, allowing agents to discover and invoke tools at runtime.

- **Structured Agent Outputs**  
  Each agent emits well‑defined JSON payloads, which are persisted to a database and exposed via REST for downstream consumption.

---

## 🔑 Key Agents

| Agent Name                     | Responsibility                                                                                           |
|--------------------------------|----------------------------------------------------------------------------------------------------------|
| **CompanyResearchAgent**       | Scrape and ingest public & proprietary sources (Crunchbase, Wikipedia, web) to produce a company profile. |
| **IndustryAnalysisAgent**      | Analyze the company profile via LLM prompts to rank and rationalize potential expansion domains.         |
| **MarketDataAgent**            | Retrieve quantitative metrics (market size, CAGR, trends) from external APIs (Google Trends, Statista). |
| **CompetitiveLandscapeAgent**  | Compile and summarize key competitors, their products, market share, and strategic positioning.          |
| **GapAnalysisAgent**           | Use LLM reasoning to detect unmet needs and strategic gaps by comparing capabilities vs. competitors.    |
| **OpportunityAgent**           | Brainstorm, validate, and rank growth opportunities grounded in data from upstream agents.               |
| **ReportSynthesisAgent**       | Aggregate all agent outputs into a citation‑rich final report (Markdown, HTML, PDF).                    |
| **CitationAgent** *(Tool)*     | On‑demand retrieval of citations or data snippets, serving all agents via the MCP tool server.          |
---


---
## 📁 Repository Structure

```text
ambitus-ai-models/
├── docs/                                       # Architecture & agent specs (Markdown)
│   ├── README.md                               # Index of spec docs
│   ├── system_overview.md
│   ├── agent_specs.md
│   ├── workflow_examples.md                    # TODO
│   └── mcp_server.md                           # TODO
├── notebooks/                                  # Experimental Jupyter/Colab prototypes
│   ├── Experiment ##- <experiment_name>.ipynb   
│   └── ...                                     # Additional experiments in ##-*.ipynb format
├── src/                          # Source code
│   ├── agents/                   # Individual agent implementations
│   │   ├── __init__.py
│   │   ├── company_research_agent.py
│   │   ├── industry_analysis_agent.py
│   │   ├── market_data_agent.py
│   │   ├── competitive_landscape_agent.py
│   │   ├── gap_analysis_agent.py
│   │   ├── opportunity_agent.py
│   │   ├── report_synthesis_agent.py
│   │   └── citation_agent.py
│   │
│   ├── mcp/                      # MCP server configuration and tools
│   │   ├── __init__.py
│   │   ├── server.py             # FastMCP server implementation
│   │   ├── tools/                # Tool implementations
│   │   │   ├── __init__.py
│   │   │   └── ...               # Individual tool modules
│   │   └── data_sources/         # Data source connectors
│   │       ├── __init__.py
│   │       └── ...               # Individual data source modules
│   │
│   ├── api/                      # Backend API for web application
│   │   ├── __init__.py
│   │   └── routes.py             # API endpoints
│   │
│   └── utils/                    # Shared utilities
│       ├── __init__.py
│       └── ...
│
├── .env.example                  # Example environment variables
├── pyproject.toml                # Project configuration and dependencies
├── README.md                     # Project overview
└── .gitignore                    # Git ignore file
```
---


---



