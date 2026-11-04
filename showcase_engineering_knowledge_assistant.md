# Engineering Knowledge Assistant

Hybrid engineering Q&A that **compares a curated document corpus with current public web results** — local RAG, one web search, one LLM synthesis call, orchestrated with LangGraph.

**[Live demo](https://frontend.livelyfield-9bf75542.westeurope.azurecontainerapps.io/)** · [Architecture](https://github.com/fbrase799/engineering_knowledge_assistant/blob/main/docs/architecture.md) · [Product overview](https://github.com/fbrase799/engineering_knowledge_assistant/blob/main/docs/product-overview.md) · [Source code](https://github.com/fbrase799/engineering_knowledge_assistant)

## Tech stack

| Layer | Technologies | Highlights |
|-------|--------------|------------|
| **Frontend** | React, TypeScript, Vite | SSE execution timeline for Hybrid / Local / Web modes |
| **Backend** | FastAPI, LangGraph, LangChain | `StateGraph` orchestration with conditional routing and hard per-question budgets |
| **RAG** | FAISS, FastEmbed MiniLM (CPU) | Shared read-only corpus; selected chunks only go to the LLM |
| **Web & generation** | Tavily, Azure OpenAI | ≤1 web search (≤3 results), ≤1 generation call |
| **Infrastructure** | Docker Compose, Azure Container Apps | Same container images locally and in the cloud |

## Request path (Hybrid)

1. `route_mode` selects Hybrid / Local / Web  
2. `retrieve_local` queries the shared FAISS index  
3. `search_web` runs one Tavily query (**question only** — no document excerpts)  
4. `assemble_context` labels and bounds evidence  
5. `evidence_gate` short-circuits when evidence is empty  
6. `generate_answer` performs one Azure OpenAI synthesis call  
7. `validate_sources` drops unknown citation IDs  

## Example question

> How does the sensor timeout handling described in our reference architecture compare with current watchdog recommendations for embedded systems?

Expect: documented approach, web findings, comparison, engineering implications (as proposals), and separated citations.

---

[← Back to profile](./README.md)
