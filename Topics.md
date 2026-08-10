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

# Part 5: AI Architecture Meets Regular Enterprise Architecture

This part connects GenAI and Agentic AI architecture with regular enterprise architecture patterns such as microservices, APIs, events, containers, Kubernetes, and cloud-native deployment.

The focus will be especially useful for architects and engineers coming from **.NET, Azure, microservices, distributed systems, and cloud architecture** backgrounds.

## 30. How GenAI Fits into Existing Enterprise Architecture

Status: Upcoming

Key idea:

> GenAI should not be designed as a separate toy system. It should fit into existing identity, APIs, data platforms, monitoring, security, and deployment architecture.

---

## 31. GenAI with Microservices Architecture

Status: Upcoming

Key idea:

> AI features should be integrated through clear service boundaries, APIs, contracts, ownership, observability, and failure handling instead of tightly coupling everything to one AI service.

---

## 32. Event-Driven AI Architecture

Status: Upcoming

Key idea:

> Event-driven patterns are useful when AI tasks are asynchronous, long-running, retriable, or triggered by business events such as invoice uploaded, claim submitted, or document processed.

Possible tools and patterns:

- Azure Service Bus
- Azure Event Grid
- Azure Functions
- Durable Functions
- Queue-based processing
- Outbox pattern
- Retry and dead-letter queues

---

## 33. Containers for AI Applications

Status: Upcoming

Key idea:

> Containers help package AI services, APIs, workers, and model-adjacent components consistently across environments.

Possible tools and patterns:

- Docker
- Azure Container Apps
- Azure Container Registry
- Containerized APIs
- Background workers
- Sidecar patterns
- Environment-specific configuration

---

## 34. Kubernetes and AKS for AI Workloads

Status: Upcoming

Key idea:

> Kubernetes or AKS may be useful for complex AI workloads that need scaling, isolation, service discovery, deployment control, and operational maturity.

Possible topics:

- When AKS is useful
- When AKS is overkill
- Scaling AI APIs and workers
- Secrets and managed identity
- Ingress and API gateway
- Observability
- Cost and operational complexity

---

## 35. API Gateway, Security, and Service Boundaries in AI Apps

Status: Upcoming

Key idea:

> AI systems still need normal enterprise API architecture: authentication, authorization, rate limits, versioning, request validation, throttling, and secure service boundaries.

Possible tools:

- Azure API Management
- Microsoft Entra ID
- OAuth / OIDC
- Managed Identity
- Key Vault
- Private endpoints
- Network restrictions

---

## 36. Choosing Azure App Service vs Azure Functions vs Container Apps vs AKS for AI Systems

Status: Upcoming

Key idea:

> The hosting choice should depend on workload type, latency, scale, runtime needs, operational complexity, cost, and team maturity.

Possible comparison:

- Azure App Service for web APIs and simple backend apps
- Azure Functions for event-driven and serverless tasks
- Azure Container Apps for containerized microservices and background workers
- AKS for complex Kubernetes-based platforms

---

## 37. Resilience Patterns for AI Microservices

Status: Upcoming

Key idea:

> AI architecture should use normal distributed-system resilience patterns such as retry, timeout, circuit breaker, bulkhead, fallback, idempotency, and dead-letter handling.

---

# Part 6: MLOps, LLMOps, and Production AI Tooling

This part covers both **MLOps theory** and **actual tools used in production AI systems**.

The goal is to help AI Architect candidates explain not only GenAI design, but also the operational lifecycle of models, prompts, data, evaluation, deployment, monitoring, and feedback.

## 38. What is MLOps and Why AI Architects Should Know It?

Status: Upcoming

Key idea:

> MLOps is about operationalizing machine learning models with repeatable pipelines, versioning, deployment, monitoring, governance, and continuous improvement.

---

## 39. ML Lifecycle: Data, Training, Evaluation, Deployment, Monitoring

Status: Upcoming

Key idea:

> AI architects should understand the full ML lifecycle, even if they are not training models every day.

Lifecycle stages:

- Data collection
- Data preparation
- Feature engineering
- Model training
- Evaluation
- Model registry
- Deployment
- Monitoring
- Feedback
- Retraining

---

## 40. Experiment Tracking and Model Registry

Status: Upcoming

Key idea:

> Experiment tracking and model registry help teams compare runs, manage versions, approve models, and deploy the right model safely.

Possible tools:

- Azure Machine Learning
- MLflow
- Azure Databricks
- Model registry
- GitHub / Azure DevOps for source control

---

## 41. Data Versioning, Feature Store, and Dataset Governance

Status: Upcoming

Key idea:

> Model quality depends heavily on data quality, dataset versioning, feature consistency, lineage, and governance.

Possible tools and concepts:

- Azure Machine Learning data assets
- Azure Databricks
- Azure Data Lake
- Microsoft Purview
- Feature store concepts
- Dataset lineage
- Data quality checks

---

## 42. CI/CD for ML and GenAI Applications

Status: Upcoming

Key idea:

> ML and GenAI systems need CI/CD not only for application code, but also for prompts, evaluation datasets, model versions, pipelines, infrastructure, and deployment configuration.

Possible tools:

- Azure DevOps
- GitHub Actions
- Azure Machine Learning pipelines
- Terraform / Bicep
- Docker
- Azure Container Registry
- Deployment approvals

---

## 43. Model Deployment Patterns

Status: Upcoming

Key idea:

> Model deployment can use online endpoints, batch endpoints, containers, APIs, serverless jobs, blue-green deployments, canary releases, and rollback strategies.

Possible tools:

- Azure Machine Learning managed online endpoints
- Azure Machine Learning batch endpoints
- Azure App Service
- Azure Functions
- Azure Container Apps
- AKS
- Azure API Management

---

## 44. Model Monitoring, Drift, Feedback, and Retraining

Status: Upcoming

Key idea:

> Production ML systems need monitoring for data drift, model drift, quality degradation, latency, errors, business metrics, and feedback loops.

Possible tools and concepts:

- Azure Machine Learning monitoring
- Azure Monitor
- Application Insights
- Log Analytics
- Custom dashboards
- Data drift
- Concept drift
- Human feedback
- Retraining triggers

---

## 45. LLMOps for Prompts, RAG, Agents, and Evaluation

Status: Upcoming

Key idea:

> LLMOps extends operational practices to prompts, RAG retrieval quality, agent tool calls, model selection, cost, latency, evaluation, safety, and feedback.

Possible areas:

- Prompt versioning
- Prompt evaluation
- RAG evaluation
- Groundedness checks
- Answer quality metrics
- Tool-call accuracy
- Token and cost monitoring
- Red-team testing
- Safety evaluation
- Human feedback

---

## 46. Actual MLOps and LLMOps Tools Used in Practice

Status: Upcoming

Key idea:

> Architects should be aware of the practical tools used across the ML and GenAI lifecycle, not only the theory.

Tool categories:

| Category | Example tools |
|---|---|
| Cloud ML platform | Azure Machine Learning |
| Experiment tracking | MLflow, Azure ML jobs |
| Model registry | Azure ML registry, MLflow registry |
| Data platform | Azure Data Lake, Azure Databricks |
| Data governance | Microsoft Purview |
| Feature engineering | Databricks, feature store concepts |
| CI/CD | Azure DevOps, GitHub Actions |
| Containers | Docker, Azure Container Registry |
| Orchestration | Azure ML pipelines, Azure Data Factory |
| Deployment | Azure ML endpoints, AKS, Container Apps, App Service |
| Monitoring | Azure Monitor, Application Insights, Log Analytics |
| Infrastructure as code | Terraform, Bicep |
| Secrets | Azure Key Vault, Managed Identity |
| GenAI evaluation | Azure AI Foundry evaluation, custom eval pipelines |
| RAG | Azure AI Search, vector indexes, hybrid search |
| Prompt / agent lifecycle | Prompt versioning, evaluation datasets, trace logs |

---

## 47. MLOps vs LLMOps vs DevOps

Status: Upcoming

Key idea:

> DevOps focuses on software delivery, MLOps focuses on ML model lifecycle, and LLMOps focuses on prompt, model, retrieval, tool, agent, and evaluation lifecycle.

---

# Part 7: Interview Answer Frameworks

## 48. How would you design an Agentic AI system?

Status: Upcoming

Key idea:

> Start with use case, users, goals, tools, data sources, agent flow, guardrails, observability, failure handling, and human escalation.

---

## 49. Design an Enterprise Document Q&A System

Status: Upcoming

Key idea:

> Cover ingestion, chunking, embeddings, vector search, metadata filtering, access control, answer generation, citations, feedback, and monitoring.

---

## 50. Design an AI Support Assistant

Status: Upcoming

Key idea:

> Support assistant should classify intent, retrieve knowledge, call tools, create tickets, escalate to humans, and learn from feedback.

---

## 51. Design an Invoice or Expense AI Agent

Status: Upcoming

Key idea:

> Useful to explain document extraction, validation, policy check, duplicate check, risk scoring, approval workflow, and notifications.

---

## 52. Explain Your GenAI Project Like a Senior Engineer

Status: Upcoming

Key idea:

> Explain problem, architecture, tradeoffs, failures, security, monitoring, and measurable impact.

---

## 53. What Failure Did You Handle in an AI Project?

Status: Upcoming

Key idea:

> Good answer should include failure, root cause, fix, prevention, and learning.

---

## 54. How Do You Measure AI System Quality?

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
