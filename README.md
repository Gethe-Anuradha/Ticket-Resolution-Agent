# Ticket-Resolution-Agent
# Ticket Resolution Agent — LangGraph Workflow

## About
This is my individual contribution (Member 5: LangGraph / Resolution Agent) to our team project **AI-Powered Ticket Resolution System**, built as part of the Infosys Springboard program.

Team repository: [Grp3_InfosysSpringboard](https://github.com/sssnehsingh/Grp3_InfosysSpringboard)

## My Role
To design and build the multi-agent resolution workflow that runs after a support ticket has been classified. This workflow retrieves relevant knowledge-base context, generates an AI response using an LLM, and automatically escalates the ticket to a human team if the issue cannot be confidently resolved.

## How It Works
The workflow is built using **LangGraph** and follows these steps:

1. **Fetch Ticket** – Retrieves ticket details (subject, description, category, severity) from the backend API.
2. **Retrieve Knowledge** – Searches the knowledge base for relevant articles related to the issue (RAG).
3. **Generate Response** – Uses an LLM (Ollama, llama3.2) to draft a step-by-step troubleshooting solution, along with a confidence score.
4. **Route** – Based on the confidence score:
   - **High confidence** → Saves the response and marks the ticket as resolved.
   - **Low confidence** → Escalates the ticket to the appropriate support team (e.g. Network Ops, Desktop Support).

## Tech Stack
- Python
- LangGraph (multi-agent workflow orchestration)
- Ollama (local LLM inference, llama3.2 model)
- Requests (REST API calls to backend)

## How to Run
```bash
pip install langgraph langchain-core requests ollama
ollama pull llama3.2

# Run with mock data (no backend required)
python agents/resolution_agent.py --demo

# Run against a real ticket (requires backend running)
python agents/resolution_agent.py --ticket-id 1
```

## Status
✅ Designed, implemented, tested, and integrated into the team repository.
