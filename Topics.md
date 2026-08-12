# Topics Roadmap

This repo will be built gradually as part of the **GenAI & AI Architect Interview Prep** series.

The focus is not only on definitions, but on practical interview answers, tradeoffs, and architect-level thinking.

This series is publicly available and free for engineers preparing for:

- GenAI interviews
- AI Architect interviews
- Solution Architect interviews
- Staff Engineer interviews
- RAG / Agentic AI / AI System Design discussions
- .NET / Azure / Microsoft-stack GenAI architecture discussions

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

Status: Completed

Key idea:

> Bad chunking leads to bad retrieval. Good chunks should preserve semantic meaning and business context.

---

## 11. Metadata Filtering and Tenant Isolation

Status: Completed

Key idea:

> In enterprise RAG, metadata filtering is critical for security, tenant isolation, and correct retrieval.

---

## 12. Vector DB is Not Enough

Status: Completed

Key idea:

> Vector database only stores and searches embeddings. Retrieval quality also depends on chunking, metadata, ranking, query rewriting, and evaluation.

---

## 13. What if the Correct Answer is Not in Top-K?

Status: Completed

Key idea:

> Top-k retrieval can miss the right answer. Use hybrid search, reranking, query expansion, better chunking, and evaluation.

---

## 14. Reducing Hallucination in RAG

Status: Completed

Key idea:

> Ground the answer in retrieved context, use citations, add confidence checks, and avoid answering when context is insufficient.

---

# Part 3: AI System Design Tradeoffs

## 15. Cost, Latency, and Accuracy Triangle

Status: Completed

Key idea:

> AI architecture is about balancing quality, speed, and cost.

---

## 16. P50, P95, and P99 Latency in LLM Apps

Status: Completed

Key idea:

> Average latency is not enough. Architects should understand tail latency because users feel slow responses during peak or failure conditions.

---

## 17. Prompt Engineering vs Guardrails vs Validation

Status: Completed

Key idea:

> Prompting guides behavior, guardrails restrict unsafe behavior, and validation checks output correctness.

---

## 18. Why Production AI Fails After Demo Success

Status: Completed

Key idea:

> Demos work in controlled cases. Production fails due to bad data, edge cases, latency, cost, hallucination, security, and lack of monitoring.

---

## 19. Fallback Design When LLM Fails

Status: Completed

Key idea:

> AI systems should have fallback flows such as retry, smaller response, deterministic path, human escalation, or graceful failure.

---

## 20. Rate Limits, Retries, and Circuit Breaker

Status: Completed

Key idea:

> LLM calls are external dependencies and should be treated like any other unreliable service.

---

## 21. Observability for AI Applications

Status: Completed

Key idea:

> Logs are not enough. Track prompts, responses, token usage, latency, retrieval quality, model version, user feedback, and failure reasons.

---

# Part 4: Enterprise GenAI Architecture and Microsoft Stack

## 22. Multi-tenant GenAI Architecture

Status: Completed

Key idea:

> Enterprise AI systems must isolate tenant data at storage, retrieval, prompt, logging, and access-control levels.

---

## 23. RBAC in AI Agents

Status: Completed

Key idea:

> AI agents should not access everything. They should act within the permission boundary of the logged-in user.

---

## 24. PII Handling in GenAI Applications

Status: Completed

Key idea:

> Sensitive data should be masked, minimized, encrypted, audited, and not unnecessarily sent to models.

---

## 25. Audit Logging and Traceability

Status: Completed

Key idea:

> In enterprise AI, you should be able to answer what data was used, what prompt was sent, what model responded, and why a decision was made.

---

## 26. Model Selection

Status: Completed

Key idea:

> Do not use the biggest model by default. Choose based on task complexity, cost, latency, accuracy, security, and evaluation results.

---

## 27. Azure OpenAI + Azure AI Search Reference Architecture

Status: Completed

Key idea:

> This topic moves from GenAI concepts to a Microsoft-stack implementation, showing how Azure AI Search, Azure OpenAI, Entra ID, Key Vault, Application Insights, and the application layer work together in an enterprise RAG architecture.

---

## 28. Semantic Kernel vs LangChain

Status: Completed

Key idea:

> AI Agents are not specific to Python, LangChain, or LangGraph. For .NET and Azure teams, Semantic Kernel is an important Microsoft-stack option, while LangChain and LangGraph are strong choices for Python-first and graph-heavy AI workflows.

---

## 29. Microsoft Agent Framework

Status: Upcoming

Key idea:

> Microsoft Agent Framework should be covered as the next Microsoft-stack agent topic because it brings together the Semantic Kernel and AutoGen direction for building, orchestrating, and deploying AI agents.

Possible angles to cover:

- What is Microsoft Agent Framework?
- How it relates to Semantic Kernel
- How it relates to AutoGen
- Why Microsoft-stack developers should track it
- How it fits .NET, Python, Azure OpenAI, Azure AI Foundry, and enterprise agents
- When to use Semantic Kernel, AutoGen, or Microsoft Agent Framework
- How it changes the Microsoft AI agent ecosystem


---

# Part 5: Model Context Protocol, Agent Interoperability, and Enterprise Tool Integration

This part explains how AI agents connect to external tools, enterprise systems, data sources, workflows, and other agents using protocol-driven integration patterns.

The focus is especially useful for engineers and architects working with **.NET, Azure, Microsoft Agent Framework, Semantic Kernel, enterprise APIs, internal systems, and secure tool integration**.

---

## 30. What is MCP and Why AI Architects Should Know It?

Status: Upcoming

Key idea:

> Model Context Protocol, or MCP, is an open protocol that helps AI applications connect to external tools, resources, prompts, data sources, and systems in a more standard way.

---

## 31. MCP vs Tool Calling vs Function Calling vs API Integration

Status: Upcoming

Key idea:

> MCP is not the same as normal tool calling or direct API integration. Tool calling is a model capability, APIs are system endpoints, and MCP provides a standard protocol layer for exposing tools, resources, and context to AI applications.

---

## 32. MCP Architecture: Host, Client, Server, Tools, Resources, and Prompts

Status: Upcoming

Key idea:

> MCP architecture should be understood through its core building blocks: host application, MCP client, MCP server, tools, resources, prompts, transport, and permission boundaries.

---

## 33. Designing MCP Servers for Enterprise APIs and Data Sources

Status: Upcoming

Key idea:

> Enterprise MCP servers should expose business capabilities safely, such as search policy, fetch claim, get expense status, retrieve document, create ticket, or call workflow APIs, without exposing uncontrolled backend access.

---

## 34. MCP Security, Identity, Permissions, and Tool Governance

Status: Upcoming

Key idea:

> MCP can make tool integration easier, but enterprise systems still need authentication, authorization, tenant isolation, RBAC, least privilege, tool approval, audit logging, prompt injection protection, and data governance.

---

## 35. MCP with Microsoft Agent Framework, Semantic Kernel, and Azure

Status: Upcoming

Key idea:

> In Microsoft-stack agentic AI systems, MCP can be used with Microsoft Agent Framework, Semantic Kernel, Azure OpenAI, Azure AI Search, Azure Functions, ASP.NET Core APIs, Entra ID, Key Vault, Application Insights, and existing enterprise services.

---

## 36. MCP Observability, Errors, Timeouts, and Production Readiness

Status: Upcoming

Key idea:

> MCP-based systems still need production engineering: timeout handling, retry policy, circuit breaker, tool-call tracing, correlation IDs, error handling, cost tracking, audit logs, monitoring, and fallback design.

---

## 37. MCP vs A2A: Tool Integration vs Agent-to-Agent Communication

Status: Upcoming

Key idea:

> MCP is mainly about connecting AI applications to tools, resources, and external systems. A2A is about communication and interoperability between agents. Architects should understand the difference because both may appear in modern agentic AI systems.

---

# Part 6: AI Architecture Meets Regular Enterprise Architecture

This part connects GenAI and Agentic AI architecture with regular enterprise architecture patterns such as microservices, APIs, events, data platforms, containers, Kubernetes, and cloud-native deployment.

The focus will be especially useful for architects and engineers coming from **.NET, Azure, microservices, distributed systems, infrastructure, and cloud architecture** backgrounds.

---

## 38. How GenAI Fits into Existing Enterprise Architecture

Status: Upcoming

Key idea:

> GenAI should not be designed as a separate toy system. It should fit into existing identity, APIs, data platforms, monitoring, security, compliance, and deployment architecture.

---

## 39. GenAI with Microservices Architecture

Status: Upcoming

Key idea:

> AI features should be integrated through clear service boundaries, APIs, contracts, ownership, observability, and failure handling instead of tightly coupling everything to one AI service.

---

## 40. Event-Driven AI Architecture

Status: Upcoming

Key idea:

> Event-driven patterns are useful when AI tasks are asynchronous, long-running, retriable, or triggered by business events such as invoice uploaded, claim submitted, document processed, or support ticket created.

---

## 41. Data Architecture for GenAI Systems

Status: Upcoming

Key idea:

> GenAI architecture depends heavily on data architecture. Architects should understand how documents, relational data, blob storage, data lake, vector indexes, metadata, lineage, access control, and retention policies fit together.

---

## 42. AI Gateway and Model Router Pattern

Status: Upcoming

Key idea:

> Enterprise AI systems may need an AI gateway or model router to centralize model access, policy enforcement, rate limits, logging, cost tracking, fallback, and model selection.

---

## 43. Containers for AI Applications

Status: Upcoming

Key idea:

> Containers help package AI services, APIs, workers, and model-adjacent components consistently across environments.

---

## 44. Kubernetes and AKS for AI Workloads

Status: Upcoming

Key idea:

> Kubernetes or AKS may be useful for complex AI workloads that need scaling, isolation, service discovery, deployment control, and operational maturity.

---

## 45. API Gateway, Security, and Service Boundaries in AI Apps

Status: Upcoming

Key idea:

> AI systems still need normal enterprise API architecture: authentication, authorization, rate limits, versioning, request validation, throttling, and secure service boundaries.

---

## 46. Choosing Azure App Service vs Azure Functions vs Container Apps vs AKS for AI Systems

Status: Upcoming

Key idea:

> The hosting choice should depend on workload type, latency, scale, runtime needs, operational complexity, cost, and team maturity.

---

## 47. Resilience Patterns for AI Microservices

Status: Upcoming

Key idea:

> AI architecture should use normal distributed-system resilience patterns such as retry, timeout, circuit breaker, bulkhead, fallback, idempotency, and dead-letter handling.

---

# Part 7: MLOps, LLMOps, and Production AI Tooling

This part covers both **MLOps theory** and **actual tools used in production AI systems**.

The goal is to help AI Architect candidates explain not only GenAI design, but also the operational lifecycle of models, prompts, data, evaluation, deployment, monitoring, and feedback.

---

## 48. What is MLOps and Why AI Architects Should Know It?

Status: Upcoming

Key idea:

> MLOps is about operationalizing machine learning models with repeatable pipelines, versioning, deployment, monitoring, governance, and continuous improvement.

---

## 49. ML Lifecycle: Data, Training, Evaluation, Deployment, Monitoring

Status: Upcoming

Key idea:

> AI architects should understand the full ML lifecycle, even if they are not training models every day.

---

## 50. Experiment Tracking and Model Registry

Status: Upcoming

Key idea:

> Experiment tracking and model registry help teams compare runs, manage versions, approve models, and deploy the right model safely.

---

## 51. Data Versioning, Feature Store, and Dataset Governance

Status: Upcoming

Key idea:

> Model quality depends heavily on data quality, dataset versioning, feature consistency, lineage, and governance.

---

## 52. CI/CD for ML and GenAI Applications

Status: Upcoming

Key idea:

> ML and GenAI systems need CI/CD not only for application code, but also for prompts, evaluation datasets, model versions, pipelines, infrastructure, and deployment configuration.

---

## 53. Model Deployment Patterns

Status: Upcoming

Key idea:

> Model deployment can use online endpoints, batch endpoints, containers, APIs, serverless jobs, blue-green deployments, canary releases, and rollback strategies.

---

## 54. Model Monitoring, Drift, Feedback, and Retraining

Status: Upcoming

Key idea:

> Production ML systems need monitoring for data drift, model drift, quality degradation, latency, errors, business metrics, and feedback loops.

---

## 55. LLMOps for Prompts, RAG, Agents, and Evaluation

Status: Upcoming

Key idea:

> LLMOps extends operational practices to prompts, RAG retrieval quality, agent tool calls, model selection, cost, latency, evaluation, safety, and feedback.

---

## 56. AI Evaluation and Quality Gates for RAG and Agents

Status: Upcoming

Key idea:

> Production GenAI systems need evaluation before and after deployment. Architects should define quality gates for retrieval quality, groundedness, hallucination, tool-call accuracy, latency, cost, safety, and user feedback.

---

## 57. Actual MLOps and LLMOps Tools Used in Practice

Status: Upcoming

Key idea:

> Architects should be aware of the practical tools used across the ML and GenAI lifecycle, not only the theory.

---

## 58. MLOps vs LLMOps vs DevOps

Status: Upcoming

Key idea:

> DevOps focuses on software delivery, MLOps focuses on ML model lifecycle, and LLMOps focuses on prompt, model, retrieval, tool, agent, and evaluation lifecycle.

---

## 59. Responsible AI, Governance, and Release Controls

Status: Upcoming

Key idea:

> Enterprise AI systems need responsible AI controls such as risk review, safety testing, data protection, explainability, human oversight, approval gates, incident handling, and compliance evidence.

---

# Part 8: Interview Answer Frameworks

This part helps convert all earlier topics into strong interview answers and system-design explanations.

The goal is to help candidates answer open-ended AI Architect, GenAI Architect, Staff Engineer, Solution Architect, and .NET / Azure Architect interview questions with structure, depth, and practical tradeoffs.

---

## 60. How would you design an Agentic AI system?

Status: Upcoming

Key idea:

> Start with use case, users, goals, tools, data sources, agent flow, guardrails, observability, failure handling, and human escalation.

---

## 61. Design an Enterprise Document Q&A System

Status: Upcoming

Key idea:

> Cover ingestion, chunking, embeddings, vector search, metadata filtering, access control, answer generation, citations, feedback, and monitoring.

---

## 62. Design an AI Support Assistant

Status: Upcoming

Key idea:

> Support assistant should classify intent, retrieve knowledge, call tools, create tickets, escalate to humans, and learn from feedback.

---

## 63. Design an Invoice or Expense AI Agent

Status: Upcoming

Key idea:

> Useful to explain document extraction, validation, policy check, duplicate check, risk scoring, approval workflow, and notifications.

---

## 64. Explain Your GenAI Project Like a Senior Engineer

Status: Upcoming

Key idea:

> Explain problem, architecture, tradeoffs, failures, security, monitoring, and measurable impact.

---

## 65. What Failure Did You Handle in an AI Project?

Status: Upcoming

Key idea:

> Good answer should include failure, root cause, fix, prevention, and learning.

---

## 66. How Do You Measure AI System Quality?

Status: Upcoming

Key idea:

> Measure retrieval quality, answer accuracy, latency, token cost, hallucination rate, tool-call accuracy, user feedback, and business outcome.

# Common Reference Scenario

Across this series, some examples use a simple enterprise scenario:

```text
Expense Management AI Agent
```

Reference file:

```text
00-common-examples/expense-management-ai-agent-scenario.md
```

This scenario helps explain concepts such as AI Agent, Tool Calling, Memory, RAG, Human-in-the-loop, Guardrails, Observability, RBAC, PII Handling, Audit Logging, Model Selection, Microsoft-stack RAG, and framework selection using one relatable business flow.

---

# About the Author

These notes are created and maintained by **Ganesh Tanaji Kumbhar**, an **AI Architect** with experience in **.NET, Azure, cloud architecture, infrastructure, enterprise application modernization, and GenAI solution design**.

I bring practical experience across:

- **.NET / C# / ASP.NET / Web API**
- **Azure App Services, Azure Functions, WebJobs, Azure SQL, Storage, Redis**
- **Cloud architecture and infrastructure modernization**
- **Application architecture and enterprise system design**
- **CI/CD, DevOps, monitoring, and production support**
- **GenAI, RAG, Agentic AI, and AI architecture patterns**

These notes are based on my real experience as both:

- An **interviewee**, facing AI, architecture, cloud, .NET, Azure, and system design rounds
- An **interviewer**, evaluating how candidates explain concepts, tradeoffs, project experience, and real-world design decisions

I write about:

- GenAI Architecture
- RAG System Design
- Agentic AI
- AI Architect Interview Preparation
- .NET and Azure Architecture
- Cloud and Enterprise AI Patterns

If you are preparing for **GenAI / AI Architect / Staff Engineer / Solution Architect / .NET Architect / Azure Architect** interviews, feel free to connect with me on LinkedIn.

🔗 **LinkedIn:** [Connect with me on LinkedIn](https://www.linkedin.com/in/gk2506/)

💬 You can also DM me on LinkedIn if you want to discuss AI architecture, interview preparation, .NET/Azure architecture, or practical GenAI learning.
