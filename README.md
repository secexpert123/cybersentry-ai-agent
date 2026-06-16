# CyberSentry AI Agent

An AI-powered network security evaluation agent built with **n8n** and **Google Gemini**. It acts as a virtual security expert taking in a network security problem, the user's analysis, and (optionally) their proposed fix, then returning a structured, prioritized scorecard.

## What It Does

1. **Collects input** through a clean web form: Problem, Analysis, and an optional Solution.
2. **Guardrail check**  if the input isn't related to network security, the agent instantly refuses with a clear message instead of attempting to answer.
3. **Evaluates the submission** and returns:
   - **What You Got Right**  praises accurate parts of the analysis
   - **What You Missed**  surfaces overlooked risks or gaps
   - **Best Appropriate Solution**  exactly 4 ranked fixes, labeled `[BEST FIX]` → `[SECONDARY FIX]` → `[DEFENSE-IN-DEPTH]` → `[ONGOING HYGIENE]`
   - **Expert Tip**  a sharp, practical insight to deepen the user's thinking
4. **Follow-up chat**  users can continue chatting with the agent afterward, and it remembers the original submission via session-based memory.
5. A **"Submit Another Problem"** button lets users restart instantly without navigating back to the original URL.

## Tech Stack

- **n8n**  workflow orchestration and AI agent framework
- **Google Gemini 2.5 Flash-Lite**  language model powering the evaluation
- **n8n Window Buffer Memory**  session-based conversational memory
- **Custom CSS**  styled form, scorecard, and button for a polished UI

## What's in This Repo

- `CyberSentry AI Agent.json`  the full exported n8n workflow (nodes, system prompt, field mappings, and CSS styling)

## How to Run It

1. Import `CyberSentry AI Agent.json` into your own n8n instance.
2. Add your Google Gemini API key as a credential (Credentials → Google Gemini API).
3. Select that credential in the **Google Gemini Chat Model** node.
4. Click **Publish**.
5. Open the **Production URL** from the form trigger node to use it live.

## Demo

*(Add your demo video link here once recorded)*

## Why I Built This

This project was built to explore AI-agent orchestration designing guardrails, structured prompt engineering, and a full end-to-end UX (input → AI evaluation → styled output → conversational follow-up) using a visual, low-code pipeline rather than hand-coded routing logic.
