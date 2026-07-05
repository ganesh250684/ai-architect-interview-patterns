# Topics Roadmap

This repo will be built gradually as part of the **AI Architect Interview Patterns** series.

The focus is not only on definitions, but on practical interview answers, tradeoffs, and architect-level thinking.

This series is publicly available and free for engineers preparing for:

* GenAI interviews
* AI Architect interviews
* Solution Architect interviews
* Staff Engineer interviews
* RAG / Agentic AI / AI System Design discussions

---

# Part 1: Agentic AI Fundamentals

## 01. When should you NOT use an AI Agent?

Status: Completed

Key idea:

> Not every problem needs an AI Agent. If the workflow is fixed, deterministic, and rule-based, a normal workflow may be better.

---

## 02. AI Agent vs Workflow vs Chatbot

Status: Completed

Key idea:

> A chatbot talks, a workflow follows fixed steps, and an AI Agent decides actions dynamically using reasoning, tools, and context.

---

## 03. What is an AI Agent? Basic vs Senior Answer

Status: Completed

Key idea:

> Do not only say “LLM + tools.” Explain reasoning, planning, tool use, memory, guardrails, and human-in-the-loop.

---

## 04. Tool Calling in AI Agents

Status: Completed

Key idea:

> Tool calling allows an LLM to interact with external systems like APIs, databases, search, ticketing systems, or business services.

---

## 05. Agent Memory

Status: Completed

Key idea:

> Memory is not just chat history. It can include session memory, user preferences, long-term memory, domain memory, and retrieved knowledge.

---

## 06. Single Agent vs Multi-Agent System

Status: Completed

Key idea:

> Multi-agent systems should be used only when responsibilities are clearly separated. Otherwise, they increase complexity.

---

## 07. Human-in-the-loop in Agentic AI

Status: Completed

Key idea:

> For high-risk decisions, the AI system should recommend, but humans should approve.

---

## Part 1 Quick Revision

Status: Completed

File:

```text
01-agentic-ai/00-agentic-ai-fundamentals-quick-revision.md
```

Key idea:

> Quick revision notes for all Agentic AI fundamentals topics before moving to RAG System Design.

---

# Part 2: RAG System Design

## 08. What is RAG?

Status: Completed

Key idea:

> RAG retrieves relevant external knowledge and gives it to the LLM as context so the answer is more grounded, accurate, and useful.

---

## 09. RAG vs Fine-tuning

Status: Completed

Key idea:

> RAG is for external knowledge at runtime. Fine-tuning is for changing model behavior, response style, format, or task-specific patterns.

---

## 10. Chunking Strategy

Status: Upcoming

Key idea:

> Bad chunking leads to bad retrieval. Good chunks should preserve semantic meaning and business context.

---

## 11. Metadata Filtering and Tenant Isolation

Status: Upcoming

Key idea:

> In enterprise RAG, metadata filtering is critical for security, tenant isolation, and correct retrieval.

---

## 12. Vector DB is Not Enough

Status: Upcoming

Key idea:

> Vector database only stores and searches embeddings. Retrieval quality also depends on chunking, metadata, ranking, query rewriting, and evaluation.

---

## 13. What if the Correct Answer is Not in Top-K?

Status: Upcoming

Key idea:

> Top-k retrieval can miss the right answer. Use hybrid search, reranking, query expansion, better chunking, and evaluation.

---

## 14. Reducing Hallucination in RAG

Status: Upcoming

Key idea:

> Ground the answer in retrieved context, use citations, add confidence checks, and avoid answering when context is insufficient.

---

# Part 3: AI System Design Tradeoffs

## 15. Cost, Latency, and Accuracy Triangle

Status: Upcoming

Key idea:

> AI architecture is about balancing quality, speed, and cost.

---

## 16. P50, P95, and P99 Latency in LLM Apps

Status: Upcoming

Key idea:

> Average latency is not enough. Architects should understand tail latency because users feel slow responses during peak or failure conditions.

---

## 17. Prompt Engineering vs Guardrails vs Validation

Status: Upcoming

Key idea:

> Prompting guides behavior, guardrails restrict unsafe behavior, and validation checks output correctness.

---

## 18. Why Production AI Fails After Demo Success

Status: Upcoming

Key idea:

> Demos work in controlled cases. Production fails due to bad data, edge cases, latency, cost, hallucination, security, and lack of monitoring.

---

## 19. Fallback Design When LLM Fails

Status: Upcoming

Key idea:

> AI systems should have fallback flows such as retry, smaller response, deterministic path, human escalation, or graceful failure.

---

## 20. Rate Limits, Retries, and Circuit Breaker

Status: Upcoming

Key idea:

> LLM calls are external dependencies and should be treated like any other unreliable service.

---

## 21. Observability for AI Applications

Status: Upcoming

Key idea:

> Logs are not enough. Track prompts, responses, token usage, latency, retrieval quality, model version, user feedback, and failure reasons.

---

# Part 4: Enterprise GenAI Architecture

## 22. Multi-tenant GenAI Architecture

Status: Upcoming

Key idea:

> Enterprise AI systems must isolate tenant data at storage, retrieval, prompt, logging, and access-control levels.

---

## 23. RBAC in AI Agents

Status: Upcoming

Key idea:

> AI agents should not access everything. They should act within the permission boundary of the logged-in user.

---

## 24. PII Handling in GenAI Applications

Status: Upcoming

Key idea:

> Sensitive data should be masked, minimized, encrypted, audited, and not unnecessarily sent to models.

---

## 25. Audit Logging and Traceability

Status: Upcoming

Key idea:

> In enterprise AI, you should be able to answer what data was used, what prompt was sent, what model responded, and why a decision was made.

---

## 26. Model Selection

Status: Upcoming

Key idea:

> Do not use the biggest model by default. Choose based on task complexity, cost, latency, accuracy, and security.

---

## 27. Azure OpenAI + Azure AI Search Reference Architecture

Status: Upcoming

Key idea:

> Common enterprise RAG architecture includes storage, ingestion pipeline, chunking, embeddings, Azure AI Search, Azure OpenAI, API layer, identity, monitoring, and feedback loop.

---

## 28. Semantic Kernel vs LangChain

Status: Upcoming

Key idea:

> Both help orchestrate LLM workflows, tools, memory, and agents. Choice depends on ecosystem, language, team skills, and enterprise fit.

---

# Part 5: Interview Answer Frameworks

## 29. How would you design an Agentic AI system?

Status: Upcoming

Key idea:

> Start with use case, users, goals, tools, data sources, agent flow, guardrails, observability, failure handling, and human escalation.

---

## 30. Design an Enterprise Document Q&A System

Status: Upcoming

Key idea:

> Cover ingestion, chunking, embeddings, vector search, metadata filtering, access control, answer generation, citations, feedback, and monitoring.

---

## 31. Design an AI Support Assistant

Status: Upcoming

Key idea:

> Support assistant should classify intent, retrieve knowledge, call tools, create tickets, escalate to humans, and learn from feedback.

---

## 32. Design an Invoice or Expense AI Agent

Status: Upcoming

Key idea:

> Useful to explain document extraction, validation, policy check, duplicate check, risk scoring, approval workflow, and notifications.

---

## 33. Explain Your GenAI Project Like a Senior Engineer

Status: Upcoming

Key idea:

> Explain problem, architecture, tradeoffs, failures, security, monitoring, and measurable impact.

---

## 34. What Failure Did You Handle in an AI Project?

Status: Upcoming

Key idea:

> Good answer should include failure, root cause, fix, prevention, and learning.

---

## 35. How Do You Measure AI System Quality?

Status: Upcoming

Key idea:

> Measure retrieval quality, answer accuracy, latency, token cost, hallucination rate, user feedback, and business outcome.

---

# Common Reference Scenario

Across this series, some examples use a simple enterprise scenario:

```text
Expense Management AI Agent
```

Reference file:

```text
00-common-examples/expense-management-ai-agent-scenario.md
```

This scenario helps explain concepts such as AI Agent, Tool Calling, Memory, RAG, Human-in-the-loop, Guardrails, and Observability using one relatable business flow.

---

# About the Author

These notes are created and maintained by **Ganesh Tanaji Kumbhar**, an **AI Architect** with experience in **.NET, Azure, cloud architecture, infrastructure, enterprise application modernization, and GenAI solution design**.

I bring practical experience across:

* **.NET / C# / ASP.NET / Web API**
* **Azure App Services, Azure Functions, WebJobs, Azure SQL, Storage, Redis**
* **Cloud architecture and infrastructure modernization**
* **Application architecture and enterprise system design**
* **CI/CD, DevOps, monitoring, and production support**
* **GenAI, RAG, Agentic AI, and AI architecture patterns**

These notes are based on my real experience as both:

* An **interviewee**, facing AI, architecture, cloud, .NET, Azure, and system design rounds
* An **interviewer**, evaluating how candidates explain concepts, tradeoffs, project experience, and real-world design decisions

I write about:

* GenAI Architecture
* RAG System Design
* Agentic AI
* AI Architect Interview Preparation
* .NET and Azure Architecture
* Cloud and Enterprise AI Patterns

If you are preparing for **GenAI / AI Architect / Staff Engineer / Solution Architect / .NET Architect / Azure Architect** interviews, feel free to connect with me on LinkedIn.

🔗 **LinkedIn:** [Connect with me on LinkedIn](https://www.linkedin.com/in/gk2506/)

💬 You can also DM me on LinkedIn if you want to discuss AI architecture, interview preparation, .NET/Azure architecture, or practical GenAI learning.
