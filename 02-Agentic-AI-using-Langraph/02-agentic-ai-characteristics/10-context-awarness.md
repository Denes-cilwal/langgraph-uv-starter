# 🧠 Context Awareness in Agentic AI

## 📌 Overview

Context awareness is a foundational capability of **Agentic AI**.  
It enables an AI system to understand what is happening, remember what has already happened, and make correct decisions across a **multi-step workflow**.

This document explains:

- Context vs Memory vs State
- How context is handled internally
- Pseudo-code for context handling
- Context-aware AI vs Stateless AI

---

## 🎯 Example Scenario Used Throughout

**Goal:**  
Hire a backend engineer

The AI is actively managing this hiring process.

---

## 🧩 Context vs Memory vs State (Very Important)

These terms are often confused, but they are **not the same**.

---

### 🔹 Context

**Context** is the **relevant information needed to make the next decision**.

It answers:

- What is the goal?
- What has already happened?
- What is happening right now?
- What rules must I follow?

#### Example Context

- Job description already posted
- 8 applications received
- Recruiter prefers remote-first candidates
- Paid ads require approval

👉 Context is **what the AI uses to decide**.

---

### 🔹 Memory

**Memory** is **where context is stored**.

There are two main types:

#### Short-Term Memory

- Current session
- Recent tool responses
- Ongoing actions

Example:

- “Calendar API returned no conflicts”

#### Long-Term Memory

- Persistent goals
- User preferences
- Policies
- Past outcomes

Example:

- “This recruiter prefers remote candidates”

👉 Memory is **storage**, not decision-making.

---

### 🔹 State

**State** is the **current status of execution**.

It answers:

- Where am I right now in the workflow?

#### Example State

- `status = "screening_candidates"`
- `status = "scheduling_interviews"`

👉 State tracks **progress**, not meaning.

---

### ✅ Summary Table

| Concept | What It Is           | Purpose           |
| ------- | -------------------- | ----------------- |
| Context | Relevant information | Decision-making   |
| Memory  | Storage              | Retention         |
| State   | Current step         | Progress tracking |

---

## 🔁 How Context Awareness Works

Context awareness is implemented by:

1. Collecting information from multiple sources
2. Storing it in memory
3. Selecting only what is relevant
4. Using it during reasoning and decision-making

---

## 🧠 Types of Context (With Examples)

### 1️⃣ Original Goal

Hire a backend engineer

### 2️⃣ Progress So Far

- Job description finalized
- Posted on LinkedIn & GitHub Jobs

### 3️⃣ Environment State

- 8 applicants so far
- LinkedIn promotion ends in 2 days

### 4️⃣ Tool Responses

- Resume parser: Candidate B has 3 years Django + AWS
- Calendar API: No conflicts at 2 PM Wednesday

### 5️⃣ User Preferences

- Remote-first candidates
- Interview questions in Google Docs

### 6️⃣ Policies / Guardrails

- Do not send offers without approval
- Do not use paid ads unless approved

---

## 🧑‍💻 Pseudo-Code: Context Handling in Agentic AI

```python
# Core context object
context = {
    "goal": "Hire backend engineer",
    "progress": {
        "job_posted": True,
        "applications_received": 8
    },
    "preferences": {
        "remote_only": True
    },
    "policies": {
        "require_offer_approval": True
    },
    "state": "screening_candidates"
}

def decide_next_action(context):
    if context["progress"]["applications_received"] < 5:
        return "Improve job visibility"

    if context["state"] == "screening_candidates":
        return "Shortlist candidates"

    return "Wait and monitor"

action = decide_next_action(context)
execute(action)

👉 The AI does not rely on prompts.
It relies on context.

```

Context-Aware AI vs Stateless AI
Stateless AI

No memory
No context
Responds only to the current prompt
Repeats questions
Cannot manage workflows

Example:

“What should I do next?”

(Forgets everything after responding

```

```
