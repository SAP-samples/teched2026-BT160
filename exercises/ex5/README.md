# Exercise 5 — Deliver the Verdict

## Overview

You have the evidence, the gaps, an outside view of the technology, and a regulatory determination. Now you turn it into the one thing the Board actually asked for: a defensible **keep / re-platform / retire** recommendation for MaMa-CRM — and you prepare to share it back to the room.

**Duration:** 15 minutes

## Step 1 — Draft the Board Verdict

⌨️ **➤ Ask the EA Assistant:**

> *"Write a Board-ready verdict on MaMa-CRM, one page maximum. Structure it as:*
> *1. **Recommendation** — keep, re-platform, or retire — stated in the first sentence.*
> *2. **Rationale** — the three to five findings that drive the recommendation, each attributed to its evidence (criterion, fact sheet field, arc42 section, or web source).*
> *3. **Top risks** — what the Board is accepting if it follows this recommendation, and what it is accepting if it does nothing.*
> *4. **Next steps** — the first three actions, each with an owner role and whether an initiative already exists in LeanIX.*
> *Keep every claim traceable to evidence we gathered. Do not introduce new facts."*

> [!TIP]
> **Why one page:** A Board decides on the summary, not the appendix. Your evidence table from Exercise 3 is the appendix; this is the page they read.

## Step 2 — Pressure-Test the Verdict

Before you present it, challenge your own recommendation once.

⌨️ **➤ Ask the EA Assistant:**

> *"Argue the opposite of your recommendation in three sentences. What is the strongest case against it, and what single piece of evidence would most change the decision if it turned out to be wrong?"*

If the counter-argument is weak, your recommendation is solid. If it is strong, you have just found the thing to say out loud in the shareback — the honest caveat that makes a recommendation credible.

## Step 3 — Capture Your Deliverable as a Governed Initiative

A recommendation that lives only in a chat session is not governed — it is ephemeral. The step that turns a verdict into a tracked piece of work is recording the successor and creating an initiative with the findings embedded.

**First — set the successor on the MaMa-CRM fact sheet.**

In Exercise 4 you created a fact sheet for the replacement platform. Bring that connection into the inventory.

⌨️ **➤ Ask the EA Assistant:**

> *"Set the replacement application we created in Exercise 4 as the successor of MaMa-CRM on the application fact sheet. Return confirmation of the update."*

**Then — create the initiative.**

⌨️ **➤ Ask the EA Assistant:**

> *"Create a LeanIX initiative to formally track the recommended action for MaMa-CRM. Name it after the recommendation (for example 'MaMa-CRM Re-platform' or 'MaMa-CRM Retirement'). In the description include: the recommendation, the top three findings that drove it with their evidence sources, and the first three next steps with owner roles. Set the status to Submitted. Set its parent initiative to 'Consolidate customer platform'. Link it to both the MaMa-CRM application fact sheet and the successor application you just recorded. Return the initiative name, ID, and URL."*

Once confirmed, open the MaMa-CRM fact sheet in the LeanIX UI and verify that the successor appears under **Successors** and the initiative appears under **Initiatives**.

> [!NOTE]
> **Why this matters:** Before this workshop, MaMa-CRM had no successor and no active initiative — the gap register in Exercise 3 correctly reported that. You have now closed both gaps in one step. The initiative carries the findings, not just a label, so anyone opening it can see what was decided, why, and who owns the next steps. Placing it as a child of **Consolidate customer platform** positions the MaMa-CRM work within the broader strategic program InDAC is running across its customer-facing application landscape — so portfolio stakeholders see it in context, not as an isolated project.

> [!TIP]
> **From portfolio decision to project execution:** A LeanIX initiative is the portfolio-level artifact — it records the decision and the evidence. When the Board approves and the project kicks off, the initiative can be connected to a project in **SAP Cloud ALM**, which tracks execution: milestones, tasks, deployment status. The initiative in LeanIX stays the authoritative record of *why* the project exists; Cloud ALM tracks *how* it is delivered. That handoff is where EA governance meets project management.

Keep the EA Assistant conversation and the MaMa-CRM fact sheet open to show the evidence trail during the shareback.

## Step 4 — Shareback

At the end of the session, be ready to tell the room:

- **What did you find?** Your recommendation and the two or three findings behind it.
- **Which path did you take?** Where the inventory, the arc42 doc, web research, and the EU AI Act check each changed your thinking.
- **What surprised you?** The conflict, the empty field, or the external fact you did not expect.

> There is no single correct verdict. A well-evidenced "re-platform" and a well-evidenced "keep with conditions" can both be right — what matters is that the recommendation is traceable to evidence, and that you are honest about the gaps.

## Optional / Speed Runner — Visualize the Architecture via MCP

If you have time before the shareback, go back to Claude Code in VS Code and generate a diagram of MaMa-CRM's landscape directly from the LeanIX workspace:

> *"Using the LeanIX MCP server, generate an architecture diagram for MaMa-CRM showing its IT component dependencies and the business capabilities it supports. Include lifecycle phases for each component."*

This uses the diagram-generation capability of the LeanIX MCP server. The result is a visual summary of the same data you explored with the EA Assistant — a useful artifact to include in a shareback deck or Board presentation.


## Summary

You have taken MaMa-CRM from an unreviewed, unloved system to a Board-ready verdict — created a governed review standard from your terminal, explored the application with the EA Assistant, reviewed it against the standard with full evidence, enriched it with web research and a regulatory check, and delivered a defensible recommendation. That is the full arc of an evidence-based application review in SAP LeanIX.

> [!NOTE]
> **Coming soon:** SAP LeanIX Reports will let you publish structured, multi-section review outputs directly from the EA Assistant into a shareable report format — no copy-paste required. Keep an eye on the LeanIX release notes for this feature.

## Going Further

If you want to take these ideas back to your own workspace:

- **[EU AI Act Classification in the EA Assistant](https://help.sap.com/docs/LEANIX/72d375467c1e4dcb872dfa2998b6328d/d4ca4b50141d4cdfb0122915e2b91f25.html)** — classify any application in your own workspace against the EU AI Act directly from the EA Assistant. A clean negative is itself a governance artifact; a positive triggers a risk category and rationale on the fact sheet. The extension must be activated under **Administration → Optional Features and Early Access**.
- **[SAP LeanIX AI Plugins and Agent Skills](https://github.com/SAP/leanix-ai-plugins)** — reusable, portable skills for Claude Code and other AI tools that package LeanIX workflows (including ADR and review patterns like the ones you ran by hand today) into installable commands.
- **[Setting up the EA Assistant](https://help.sap.com/docs/leanix/ea/setting-up-enterprise-architecture-assistant)** — how to upload and index your own documents so the EA Assistant can reason over them, exactly as it did with the arc42 doc and the criteria PDF.
- **[Connecting to the MCP Server](https://help.sap.com/docs/leanix/ea/connecting-to-mcp-server)** — connect your own workspace to Claude Code, Cursor, or any MCP client, with either a technical-user API token or user-based OAuth.
- **[EA Assistant — What's New](https://help.sap.com/whats-new/cf0cb2cb4d954c7c9aad66dca6f71305?locale=en-US&Component=SAP+LeanIX)** — recent releases for the EA Assistant, including new document reasoning, EU AI Act classification, and diagram generation via MCP.
- **[LeanIX MCP Server — Release Notes](https://help.sap.com/docs/leanix/ea/release-notes-mcp-server)** — changelog for the LeanIX MCP server, including new tools and authentication options.

[Back: Exercise 4](../ex4/README.md) | [Return to Overview](../../README.md)
