# Exercise 1 — Create the Review Standard from Claude Code (via MCP)

## Overview

Before you can review MaMa-CRM against anything, the review standard needs to exist *inside* LeanIX — not as a PDF on a shared drive, but as a governed **Architecture Decision Record (ADR)** that every future review can be checked against. In this exercise you use **Claude Code** (already connected to your LeanIX workspace from Getting Started) to first explore MaMa-CRM through the MCP server, then create the review-standard ADR.

This is the one exercise where you work from your own developer toolchain rather than the LeanIX UI — it shows that the same workspace data is reachable from both surfaces.

**Duration:** 20 minutes

## Background

InDAC's architecture group recently published the **Application Review — Top 20 Criteria** standard. Right now it only lives as a document. For the Board review to be defensible, the standard has to become a traceable record in the system of record — so that the verdict you deliver at the end of the session can point back to an approved decision, not a file attachment.

You *could* create that ADR by clicking through the LeanIX UI. Instead, you'll do it from **Claude Code**, talking to LeanIX over the **Model Context Protocol (MCP)**.

> [!NOTE]
> **What is MCP?** The Model Context Protocol is an open standard that lets an AI assistant call external tools and systems in a structured way. The **LeanIX MCP server** exposes your workspace — fact sheets, architecture decisions, inventory search — as tools that an assistant like Claude Code can call directly. In practice: you describe what you want in plain language, and the assistant performs real operations in your LeanIX workspace.

> [!NOTE]
> **Why start here?** It makes one thing concrete up front: LeanIX is not a walled garden. The architecture data you'll work with in the UI for the rest of the session is the *same* data a developer can reach from their own toolchain. Create once, govern everywhere.

## Step 1 — Explore MaMa-CRM via MCP

Claude Code is already connected to your workspace from Getting Started. Start by using it to explore the application you are about to review — this is both a useful orientation and a confirmation that the MCP connection works end-to-end.

⌨️ **➤ In the Claude Code chat in VS Code, ask:**

> *"Using the LeanIX MCP server, look up the MaMa-CRM application fact sheet and show me all its relations — the IT components, business capabilities, interfaces, and any other fact sheets it is connected to. For each relation include the name and lifecycle phase where available."*

Claude Code will call the MCP server and return what it finds in your workspace. Read the output — you will recognize this application and its dependency landscape again when the EA Assistant describes it from Exercise 2 onward.

> [!NOTE]
> Claude Code called real tools in your live LeanIX workspace — not a demo environment, not mocked data. You are reading actual inventory records. If Claude Code reports that MaMa-CRM does not exist or returns an authentication error, re-check the MCP connection from Getting Started.

## Step 2 — Create the Review-Standard ADR

Now create the Architecture Decision that captures InDAC's review standard.

⌨️ **➤ Paste this into Claude Code:**

> *"Using the LeanIX MCP server, create an architecture decision titled 'Application Review — Top 20 Criteria Standard'. Set its status to Accepted. Populate it as follows:*
> - *Context: InDAC's architecture group has published a Top 20 Criteria standard — the universally applicable, immediately verifiable criteria used for portfolio rationalisation, M&A due diligence, and governance escalations. Every application review must now be assessed against this standard.*
> - *Decision: All application reviews at InDAC are evaluated against the Top 20 Criteria. Each criterion is assessed as Pass or Gap, with evidence. A review informs a keep / re-platform / retire recommendation.*
> - *Consequences: Reviews become comparable across the portfolio and traceable to an approved standard. Applications with unaddressed Gaps on gate criteria cannot be recommended for continued investment without a remediation plan.*
> *Set me as the approver, and set Last Reviewed to today. Then return the ADR's ID and URL."*

Claude Code will call `create_architecture_decision` and report back the new ADR's ID and URL.


## Step 3 — Confirm It Landed in LeanIX

1. Open LeanIX in your browser (the tab from Getting Started).
2. Navigate to **Architecture Decisions**.
3. Search for the decision title and open your ADR.
4. Confirm the **Context**, **Decision**, and **Consequences** sections match what you created — and that the status is **Accepted**.
5. If **Approved by** is empty, click **Edit** and add your LeanIX user ID.

> [!IMPORTANT]
> **This is the handoff.** You created this record from Claude Code, and it is now a first-class object in the LeanIX workspace — visible in the UI, ready to be linked to fact sheets, and readable by the EA Assistant. From here on, you work inside LeanIX.

## Summary

You used Claude Code to explore MaMa-CRM's inventory data via MCP, then created the review-standard ADR from your terminal. The standard that was a PDF five minutes ago is now a governed, traceable Architecture Decision. In Exercise 2, you'll switch to the LeanIX EA Assistant and explore MaMa-CRM's landscape in more depth.

[Back: Getting Started](../ex0/README.md) | [Next: Exercise 2 — Explore MaMa-CRM with the EA Assistant](../ex2/README.md)
