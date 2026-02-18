# Financial Research Agent

A powerful, agentic AI system designed to perform in-depth financial research on companies. It orchestrates a team of specialized AI agents to plan searches, gathering data, analyze fundamentals and risk, and compile a comprehensive financial report.

## 🚀 Features

*   **Intelligent Planning:** Breaks down complex queries into specific search actions.
*   **Multi-Agent Architecture:**
    *   **Planner:** Strategizes the research process.
    *   **Searcher:** Gathers relevant information from the web.
    *   **Financial Analyst:** Analyzes key metrics, revenue, profit, and growth.
    *   **Risk Analyst:** Identifies potential red flags and risks.
    *   **Writer:** Synthesizes findings into a coherent markdown report.
    *   **Verifier:** Fact-checks the report against source data.
*   **Traceability:** Full visibility into the agent's thought process and execution trace.

## 🛠️ Architecture

The system uses a manager-delegate pattern where the `FinancialResearchManager` coordinates the workflow:

1.  **Planning:** The `planner_agent` generates a list of targeted search queries based on the user's request.
2.  **Execution (Search):** The `search_agent` executes the queries in parallel to gather raw information.
3.  **Analysis & Writing:** The `writer_agent` utilizes the `financials_agent` and `risk_agent` as tools to process the search results and draft the report.
4.  **Verification:** The `verifier_agent` reviews the final report to ensure accuracy and consistency.

## 📦 Installation

### Prerequisites

*   Python 3.10+
*   OpenAI API Key

### Setup

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/yourusername/financial-research-agent.git
    cd financial-research-agent
    ```

2.  **Create a virtual environment:**
    ```bash
    python3 -m venv .venv
    source .venv/bin/activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Configure Environment:**
    Create a `.env` file in the root directory:
    ```bash
    touch .env
    ```
    Add your OpenAI API key:
    ```env
    OPENAI_API_KEY=your_api_key_here
    ```

## 🚀 Usage

Run the agent interactively:

```bash
python main.py
```

Enter your research query when prompted. For example:

> "Write up an analysis of Apple Inc.'s most recent quarter."

The agent will display its progress in real-time and output the final report, follow-up questions, and verification results to the console.

## 📁 Project Structure

```
financial_research_agent/
├── research_agents/      # Agent definitions (Planner, Search, Writer, etc.)
├── examples/             # Example scripts
├── main.py               # Entry point
├── manager.py            # Orchestration logic
├── printer.py            # Console output utilities
├── requirements.txt      # Project dependencies
└── README.md             # Documentation
```
