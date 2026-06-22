# AI Architect Interview Pattern #1

# When Should You NOT Use an AI Agent?

---

## Question

In an interview, you may be asked:

> When should you not use an AI Agent?

Or:

> Do we need an AI Agent for every GenAI use case?

Or:

> How do you decide between a normal workflow and an AI Agent?

---

## Why interviewer asks this

The interviewer is not only checking whether you know AI Agents.

They are checking whether you can think like an architect.

A junior answer may be:

> We can use AI Agents to automate everything.

A senior or architect-level answer should be:

> We should use AI Agents only when the problem needs reasoning, planning, tool selection, dynamic decision-making, or interaction with multiple systems. If the process is fixed and deterministic, a normal workflow is usually better.

This question tests your understanding of:

* Tradeoffs
* Cost
* Latency
* Reliability
* Maintainability
* Testability
* Production readiness
* Whether AI is actually required or not

---

## Basic answer

You should not use an AI Agent when the process is simple, fixed, and rule-based.

If the same steps happen every time, and there is no need for reasoning or decision-making, then a normal workflow, API orchestration, scheduled job, or rules engine may be better.

---

## Architect-level answer

I would not use an AI Agent by default.

First, I would check whether the use case actually needs agentic behavior.

An AI Agent is useful when the system needs to:

* Understand user intent
* Reason over context
* Decide the next action
* Select tools dynamically
* Work with incomplete information
* Ask follow-up questions
* Use memory
* Coordinate multiple steps
* Escalate based on situation

But if the business process is predictable and deterministic, I would avoid an AI Agent.

For example, if the requirement is:

> Read invoice records every night, validate mandatory fields, calculate tax, and send a report.

This does not need an AI Agent.

A scheduled job, workflow engine, Azure Function, Logic App, background service, or rules engine can solve this more reliably.

AI Agents add flexibility, but they also add:

* Extra cost
* Extra latency
* Non-deterministic behavior
* Testing complexity
* Monitoring complexity
* Security concerns
* Failure handling complexity

So my approach is:

> Use deterministic systems wherever possible. Use AI Agents only where reasoning, dynamic decision-making, and tool selection are actually needed.

---

## Must mention in interview

When answering this question, try to mention these points:

### 1. Do not use AI just because it is trending

Architects should not force AI into every problem.

A good architect chooses the simplest reliable solution.

---

### 2. Prefer deterministic workflow for fixed processes

If steps are already known, fixed, and rule-based, use:

* Workflow engine
* API orchestration
* Rules engine
* Scheduled job
* Queue-based processing
* Azure Function
* Logic App
* Background worker

These are easier to test, monitor, and control.

---

### 3. AI Agent is useful for dynamic decision-making

Use Agentic AI when the system needs:

* Reasoning
* Planning
* Tool selection
* Context understanding
* Multi-step decisions
* Memory
* Human-like interaction
* Handling ambiguous user requests

---

### 4. Mention cost and latency

AI Agent usually requires multiple LLM calls.

Multiple LLM calls mean:

* Higher token cost
* Higher response time
* More dependency on external model availability
* More chances of failure

---

### 5. Mention reliability and testing

Traditional workflows are easier to test because the path is predictable.

AI Agents are harder to test because output may vary depending on prompt, model, context, tools, and retrieved data.

---

### 6. Mention security

AI Agents may access tools, APIs, databases, or enterprise systems.

So we need:

* Proper authentication
* Authorization
* RBAC
* Tool-level permission checks
* Audit logs
* Input/output validation
* Human approval for sensitive actions

---

### 7. Mention human-in-the-loop

For high-risk decisions, AI should not directly execute everything.

It should recommend, explain, and ask for approval where needed.

---

## Real-world example

### Example 1: No AI Agent needed

Requirement:

> Every day at 10 PM, fetch all approved expenses, generate a report, and email it to finance.

This is fixed and predictable.

Better solution:

* Scheduled job
* Azure Function timer trigger
* SQL query
* Report generation
* Email service

No AI Agent needed.

---

### Example 2: AI Agent may be useful

Requirement:

> Employee asks: “Why was my hotel expense rejected and what can I do next?”

Here, the system may need to:

* Understand the employee question
* Retrieve expense details
* Check policy
* Compare claimed amount with allowed limit
* Explain rejection reason
* Suggest next step
* Raise support ticket if required
* Escalate to manager if exception is valid

This may be a good use case for an AI Agent because the flow is dynamic and depends on user intent and context.

---

## Common mistake

Many candidates say:

> We can use AI Agent to automate this process.

But they do not explain:

* Why agent is needed
* Why normal workflow is not enough
* What tools the agent will use
* What can go wrong
* How they will control the agent
* How they will handle cost, latency, and security

This sounds tool-focused, not architect-level.

---

## Better interview answer

A strong answer can be:

> I would not use an AI Agent for every use case. If the process is fixed, rule-based, and predictable, I prefer deterministic workflows because they are cheaper, faster, easier to test, and more reliable. I use AI Agents when the system needs reasoning, tool selection, planning, memory, or dynamic decision-making. For example, a nightly invoice validation job does not need an agent, but an assistant that understands invoice issues, checks policy, asks for missing information, calls tools, and escalates exceptions may be a good agentic use case.

---

## One-line answer

> Do not use an AI Agent when a deterministic workflow can solve the problem more reliably, cheaply, and predictably.

---

## Memory formula

Use this formula:

# Fixed Flow = Workflow

# Dynamic Decision = Agent

Or:

# Rules First, Agent Later

Meaning:

If rules and steps are clear, use normal workflow.

If reasoning, tool selection, and dynamic decision-making are needed, consider an AI Agent.

---

## Interview closing line

You can close your answer like this:

> As an architect, my responsibility is not to use AI everywhere. My responsibility is to choose the simplest architecture that meets reliability, cost, security, and business requirements. AI Agents are powerful, but they should be used only when they add real value over deterministic workflows.

---

## Related upcoming topics

* AI Agent vs Workflow vs Chatbot
* What is an AI Agent? Basic vs Senior Answer
* Tool Calling in AI Agents
* Agent Memory
* RAG vs Agent vs Fine-tuning
* How to design an Agentic AI system


---

## About the Author

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
