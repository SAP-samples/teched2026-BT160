# Exercise 2 — Explore MaMa-CRM with the EA Assistant

## Overview

You have created the review standard. Before you judge MaMa-CRM against it, you need to understand what MaMa-CRM actually *is* in the landscape — its lifecycle, who owns it, what it depends on, and what business capabilities it supports. In this exercise you switch to the **EA Assistant** inside SAP LeanIX and explore the application in natural language.

From here to the end of the workshop, you work entirely inside the LeanIX UI.

**Duration:** 25 minutes

## Background

The **EA Assistant** is the conversational AI built into SAP LeanIX — you reach it through the LeanIX interface, no setup required. It works by calling the same **MCP server** you connected Claude Code to in Exercise 1, but it also has access to the documents indexed in your workspace. This means everything you just created from Claude Code is immediately visible to the EA Assistant. The architecture decision you created is already in the workspace — the EA Assistant can read it, cite it, and reason over it.

An application review stands or falls on evidence. The EA Assistant reads the MaMa-CRM fact sheet and traverses its relationships — so instead of clicking through tabs and relation explorers by hand, you ask questions and it gathers the facts. Just as importantly, it tells you what is *missing*: a null field or a relationship with zero edges is itself a finding when you are reviewing governance maturity.

## Step 1 — Open the EA Assistant and Review the ADR

1. In SAP LeanIX, navigate to **More** (top header) → **EA Assistant**.
2. A conversational panel opens. Start by pulling up the architecture decision you created from Claude Code:

**➤ Ask the EA Assistant:**

> *"Find the architecture decision titled 'Application Review — Top 20 Criteria Standard'. Show me its full content: the context, decision statement, and consequences."*

You should see the ADR you created in Exercise 1, with the context, decision, and consequences exactly as you defined them. If it does not appear, navigate to **Architecture Decisions** in the UI to confirm it was saved — then ask again.

> [!NOTE]
> This shows the same data through two lenses. You created the ADR from your terminal via MCP; the EA Assistant reads it from the same workspace. This is what "govern everywhere" means in practice — and it confirms that the review standard the EA Assistant will reason over for the rest of the session is the one you just created, not an assumption.

> [!TIP]
> If the ADR is not linked to the MaMa-CRM application, ask: *"Link the 'Application Review — Top 20 Criteria Standard' architecture decision to the MaMa-CRM application."*

> [!TIP]
> The EA Assistant keeps context within a conversation. Stay in one session through this exercise so it remembers what it has already looked up about MaMa-CRM.

## Step 2 — Get the Shape of the Application

Start broad.

**➤ Ask the EA Assistant:**

> *"Summarize the MaMa-CRM application fact sheet: its lifecycle phase, business criticality, functional and technical fit, hosting type, and completion percentage. For any field that is empty, say so explicitly."*

Read the response. Note which fields carry real values and which are empty — the empty ones are candidate gaps for your review.

> [!NOTE]
> "The field is empty" is not a dead end — it is evidence. Several of the Top 20 Criteria require a value to simply *exist* in the authoritative inventory (for example, an assigned business-criticality rating). A blank field fails that bar regardless of how the application actually behaves.

## Step 3 — Map Ownership and Accountability

**➤ Ask the EA Assistant:**

> *"Who is subscribed to MaMa-CRM and in which roles? Is there a responsible owner, and are there any accountable or observer subscriptions? List any ownership gaps."*

The scenario told you MaMa-CRM is "the system nobody fully owns anymore." Confirm whether the inventory data backs that up.

## Step 4 — Trace the Dependencies

**➤ Ask the EA Assistant:**

> *"What IT components does MaMa-CRM depend on? For each component, give its lifecycle phase and provider, and flag any that are at or past end of life. Then list the business capabilities MaMa-CRM supports and any data objects it reads or writes."*

MaMa-CRM is built on Java, Oracle, and the Drools rule engine. Technology currency is one of the review criteria — see whether the inventory records those components and their support status, or whether that information is missing.

> [!NOTE]
> Dependencies are where risk hides. An application can look healthy on its own fact sheet while sitting on a database version that lost vendor support two years ago. The EA Assistant surfaces that in one question instead of a manual traversal.

## Step 5 — Build Your Landscape Notes

Finish the exercise with a consolidation prompt.

**➤ Ask the EA Assistant:**

> *"Based on everything you have gathered about MaMa-CRM so far, give me a short structured briefing: what we know, what is missing from the inventory, and the three things that most concern you ahead of a formal review. Attribute each point to the fact sheet field or relation it came from."*

The EA Assistant will keep this briefing in its conversation context. You will reference it when you run the full assessment in Exercise 3.

## Summary

You now have a grounded picture of MaMa-CRM: its lifecycle and criticality, its ownership gaps, its technology dependencies, and its business-capability coverage — along with an explicit list of what the inventory does *not* record. In Exercise 3, you will take this picture and evaluate it criterion by criterion against the Top 20 Criteria standard, with the arc42 documentation as your second source of evidence.

[Back: Exercise 1](../ex1/README.md) | [Next: Exercise 3 — Review MaMa-CRM Against the Standard](../ex3/README.md)
