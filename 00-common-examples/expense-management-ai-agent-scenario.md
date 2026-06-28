# Common Example Scenario: Expense Management AI Agent

This document explains the simple business scenario used across the **AI Architect Interview Patterns** series.

The goal is not to explain a complex expense product.

The goal is to provide a common, easy-to-understand example so that readers can relate to AI Agent concepts such as:

* Tool Calling
* Agent Memory
* RAG
* Single Agent vs Multi-Agent
* Guardrails
* Human-in-the-loop
* Observability

---

## Simple Scenario

Imagine an employee submitted a hotel expense.

Later, the expense was rejected.

Now the employee wants to know:

> Why was my hotel expense rejected, and what should I do next?

Instead of searching through multiple screens, policy documents, approval comments, and emails, the employee can ask an AI assistant.

The AI assistant helps the employee understand the reason in simple language.

---

## Example User Question

```text
My hotel expense was rejected. Why was it rejected, and can I resubmit it?
```

---

## What the AI Assistant Should Do

At a high level, the AI assistant should help the employee with these things:

1. Understand what the user is asking
2. Find the related expense
3. Check the current expense status
4. Check why the expense was rejected
5. Check the related expense policy
6. Explain the reason in simple language
7. Suggest the next possible action

---

## Simple Example

### Expense Details

```text
Expense ID: EXP-1024
Category: Hotel
Submitted Amount: ₹8,500
Status: Rejected
Receipt Status: Missing
```

### Policy Details

```text
Allowed Hotel Limit: ₹6,000
Receipt Required: Yes
Exception Approval: Allowed with manager approval
```

### Rejection Reason

```text
Amount exceeds allowed limit and receipt is missing.
```

---

## Example Assistant Response

```text
Your hotel expense EXP-1024 was rejected for two reasons:

1. The submitted amount was ₹8,500, but the allowed hotel limit for your grade is ₹6,000.
2. The hotel receipt is missing.

You can upload the missing receipt and resubmit the expense.

Since the amount is above the allowed limit, manager approval may be required.
```

---

## Simple Functional Flow

```text
Employee asks question
        ↓
AI assistant finds the expense
        ↓
AI assistant checks rejection reason
        ↓
AI assistant checks policy
        ↓
AI assistant explains the issue
        ↓
AI assistant suggests next action
```

---

## What the User May Ask Next

After getting the first answer, the employee may ask follow-up questions like:

```text
Can I upload the receipt now?
```

```text
Can I resubmit this expense?
```

```text
Can this be escalated to my manager?
```

```text
What is the hotel reimbursement policy?
```

```text
Can you create a support ticket for this?
```

The AI assistant should continue the conversation based on the same expense context.

---

## Why This Example Is Used in the Series

This example is simple but useful.

It has enough functionality to explain many AI architecture concepts without changing the business scenario again and again.

For example:

* When we discuss **Tool Calling**, the assistant may call tools to fetch expense details or approval history.
* When we discuss **Agent Memory**, the assistant may remember that the user is talking about expense `EXP-1024`.
* When we discuss **RAG**, the assistant may retrieve the latest expense policy.
* When we discuss **Single Agent vs Multi-Agent**, the same example can show when one agent is enough and when multiple specialized agents may help.
* When we discuss **Guardrails**, the assistant should not approve or reject expenses without proper permission.

Readers can refer to this file whenever an example in the series talks about an expense rejection scenario.

---

## Very Short Summary

> An employee asks why an expense was rejected. The AI assistant checks expense details, policy, and approval reason, then explains the issue and suggests the next action.

---

# Optional: Detailed Functional Explanation

This section is optional.

You can skip this section if you only want to understand the basic example.

The details below are added for readers who want slightly more functional context.

---

## Possible Expense Statuses

An expense may have statuses like:

* Draft
* Submitted
* Pending Manager Approval
* Pending Finance Review
* Approved
* Rejected
* Needs Clarification
* Resubmitted
* Paid

---

## Common Rejection Reasons

An expense may be rejected because:

* Receipt is missing
* Amount exceeds allowed limit
* Expense category is incorrect
* Expense is duplicate
* Expense date is invalid
* Business purpose is missing
* Expense was submitted late
* Manager rejected the expense
* Finance rejected the expense

---

## Possible User Actions

After understanding the rejection reason, the employee may choose to:

* Upload missing receipt
* Correct expense category
* Add business purpose
* Resubmit expense
* Request manager approval
* Create support ticket
* Cancel the expense

---

## Simple Functional Modules

A real expense system may have these modules:

### 1. Expense Submission

Employee submits expense details such as:

```text
Category
Amount
Date
Location
Receipt
Business purpose
Project or cost center
```

### 2. Expense Validation

The system validates basic details.

Example:

```text
Is receipt required?
Is amount entered?
Is expense date valid?
Is category selected?
```

### 3. Policy Check

The system checks company rules.

Example:

```text
Hotel limit for employee grade L5 is ₹6,000.
Submitted amount is ₹8,500.
The expense exceeds the allowed limit.
```

### 4. Approval Workflow

The expense goes through review.

Example:

```text
Employee submits expense
        ↓
Manager reviews
        ↓
Finance reviews
        ↓
Approved or rejected
```

### 5. Resubmission

If correction is allowed, the employee can update details and resubmit.

Example:

```text
Employee uploads missing receipt
        ↓
Employee resubmits expense
        ↓
Manager or finance reviews again
```

### 6. Support Ticket

If the user still needs help, a support ticket can be created.

Example:

```text
Ticket Type: Expense Rejection Clarification
Expense ID: EXP-1024
Status: Open
Assigned Team: Expense Support
```

---

## Example Functional APIs

These are simple example functions that the AI assistant may use.

### GetExpenseDetails

Purpose:

```text
Fetch expense details by expense ID.
```

Example output:

```json
{
  "expenseId": "EXP-1024",
  "category": "Hotel",
  "amount": 8500,
  "currency": "INR",
  "receiptStatus": "Missing",
  "approvalStatus": "Rejected",
  "rejectionReason": "Amount exceeds allowed limit and receipt is missing"
}
```

---

### GetExpensePolicy

Purpose:

```text
Fetch applicable expense policy.
```

Example output:

```json
{
  "category": "Hotel",
  "allowedLimit": 6000,
  "currency": "INR",
  "receiptRequired": true,
  "exceptionAllowed": true,
  "managerApprovalRequired": true
}
```

---

### GetApprovalHistory

Purpose:

```text
Fetch approval status and approver comments.
```

Example output:

```json
{
  "expenseId": "EXP-1024",
  "approvalStatus": "Rejected",
  "approverRole": "Manager",
  "comments": "Receipt missing and amount exceeds hotel limit"
}
```

---

### UploadReceipt

Purpose:

```text
Upload or attach a missing receipt.
```

Example output:

```json
{
  "expenseId": "EXP-1024",
  "receiptStatus": "Attached",
  "message": "Receipt uploaded successfully"
}
```

---

### ResubmitExpense

Purpose:

```text
Resubmit a corrected expense.
```

Example output:

```json
{
  "expenseId": "EXP-1024",
  "status": "Resubmitted",
  "nextStep": "Pending Manager Approval"
}
```

---

### CreateSupportTicket

Purpose:

```text
Create a support ticket for manual help.
```

Example output:

```json
{
  "ticketId": "TCK-5501",
  "status": "Open",
  "assignedTeam": "Expense Support"
}
```

---

## Final Note

This file is only a **common functional reference** for the series.

It is intentionally kept simple so that readers can understand the business context without needing deep knowledge of expense management systems.

---

## One-line summary

> This scenario shows how an AI assistant can help an employee understand a rejected expense, check the reason, explain the policy, and suggest the next action.

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
