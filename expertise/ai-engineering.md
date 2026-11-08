# AI Engineering

My view: AI is most valuable when it is **engineered into the delivery system** — with clear boundaries, budgets, and evidence — not bolted on as a demo.

I use AI in two complementary ways:

1. **AI-assisted development** — Spec-Driven Design, GitHub Copilot, Cursor, and Claude Code to raise the quality and speed of design and implementation while keeping humans accountable for architecture and review.
2. **AI-powered systems** — LangChain, LangGraph, RAG, and LLM runtimes (cloud or local) to build assistants and workflows that answer real engineering questions under explicit constraints (call limits, source validation, traceability).

## Use cases I address

* **Hybrid RAG** — answer questions from a **local, controlled document corpus** (secure / internal knowledge) and, when useful, **compare with current public web results**. Evidence stays labeled; retrieval and generation stay budgeted. See the [Engineering Knowledge Assistant](../showcase_engineering_knowledge_assistant.md).
* **Secure GenAI on local models** — LangChain (and LangGraph) to wire retrieval and tools against **Ollama**-hosted models so sensitive context can stay on-prem or on a developer machine instead of leaving for a public API.
* **AI in the software lifecycle** — Spec-Driven Design and coding assistants (Copilot, Cursor, Claude Code) to accelerate design and implementation without giving up architectural ownership.

I prefer prototypes that show **orchestration, failure modes, and cost control**, not only happy-path prompts.

**Keywords:** Spec-Driven Design · LangChain · LangGraph · RAG · Ollama · Python · GitHub Copilot · Cursor · Claude Code

---

[← Back to profile](../README.md)
