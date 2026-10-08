# Exercise 1 — Create the Review Standard from Claude Code (via MCP)

## Overview

Before you can review MaMa-CRM against anything, the review standard needs to exist *inside* LeanIX — not as a PDF on a shared drive, but as a governed **Architecture Decision Record (ADR)** that every future review can be checked against. In this exercise you connect **Claude Code** to your LeanIX workspace through the **MCP server** and create that ADR from your terminal.

Apart from a quick trip into the LeanIX admin area to mint an access token, this is the one exercise where you work outside the LeanIX UI — it shows that the same workspace you'll use for the rest of the session is also reachable from your own developer tools.

**Duration:** 20 minutes

## Background

InDAC's architecture group recently published the **Application Review — Top 20 Criteria** standard. Right now it only lives as a document. For the Board review to be defensible, the standard has to become a traceable record in the system of record — so that the verdict you deliver at the end of the session can point back to an approved decision, not a file attachment.

You *could* create that ADR by clicking through the LeanIX UI. Instead, you'll do it from **Claude Code**, the AI coding assistant available on your session laptop, talking to LeanIX over the **Model Context Protocol (MCP)**.

> **What is MCP?** The Model Context Protocol is an open standard that lets an AI assistant call external tools and systems in a structured way. The **LeanIX MCP server** exposes your workspace — fact sheets, architecture decisions, inventory search — as tools that an assistant like Claude Code can call directly. In practice: you describe what you want in plain language, and the assistant performs real operations in your LeanIX workspace.

> **Why start here?** It makes one thing concrete up front — LeanIX is not a walled garden. The architecture data you'll work with in the UI for the rest of the session is the *same* data a developer can reach from their own toolchain. Create once, govern everywhere.

## Step 1 — Confirm Claude Code Is Available

Your session laptop has **Claude Code** pre-installed.

1. Open a terminal.
2. Verify the CLI is on your path:

   ```bash
   claude --version
   ```

   You should see a version number. If the command is not found, raise your hand — your trainer will help before you continue.

> **Did you run `LMU_BT160`?** If you skipped the laptop setup in Getting Started, do it now (Start menu → `bt160` → run `LMU_BT160`). Without the proxy setup, the next steps will fail to reach LeanIX.

## Step 2 — Create Your Technical-User API Token

The MCP server authenticates with a **technical-user API token** from your workspace. You are the admin of your own workspace, so you create this token yourself. It is a one-time, two-minute task.

1. In SAP LeanIX, open the **user profile menu** (top right) and select **Administration**.
2. Go to **Technical Users**.
3. Click **Create Technical User** (or **New Technical User**).
4. Give it a descriptive name — for example, `claude-code-mcp` — and assign the **Admin** permission role so it can create architecture decisions.
5. Click **Create**. An **API token** is generated and shown.
6. **Copy the token immediately and keep it somewhere handy for the next step.**

> **⚠️ The token is shown only once.** If you navigate away before copying it, you cannot retrieve it — you will have to create another technical user and generate a new token. Copy it now.

> **What is a technical user?** A technical user is a non-human service account used for programmatic access. The token it carries is what lets Claude Code act in your workspace over the MCP server, instead of a browser login.

## Step 3 — Register the LeanIX MCP Server

You will now add the LeanIX MCP server to Claude Code using your workspace's MCP endpoint and the token you just created. The server speaks HTTP transport and authenticates with the **technical-user API token** passed as a request header.

The endpoint follows this shape (your workspace URL is on your session card):

```
https://<workspace-subdomain>.leanix.net/services/mcp-server/v1/mcp
```

1. From your terminal, register the server with Claude Code. Replace `<MCP-URL>` with your workspace's MCP endpoint and `<API-TOKEN>` with the token from Step 2:

   ```bash
   claude mcp add --transport http leanix <MCP-URL> \
     --header "Authorization: Token <API-TOKEN>"
   ```

   > **Note the auth scheme:** the header value is `Token <API-TOKEN>` — *not* `Bearer`. The LeanIX MCP server expects the `Token` scheme with a technical-user API token. Using `Bearer` will fail authentication.

2. List your configured servers to confirm it registered:

   ```bash
   claude mcp list
   ```

   You should see `leanix` in the list.

> **Why a technical-user token (not a browser login)?** The token you minted in Step 2 lets Claude Code authenticate in a single command, with no interactive login flow in the terminal. (The MCP server also supports OAuth for individual user-based access — handy in your own organization — but the token is the fastest path here.)

> **Where this is stored:** `claude mcp add` writes the server into your Claude Code configuration, including the header. For a project-scoped setup you can also commit a `.mcp.json` file to a repo — but for this workshop the single `add` command above is all you need.

## Step 4 — Verify the Connection

Because the token is already in the header you registered, there is no separate login step — Claude Code is authenticated the moment the server is added.

1. Start Claude Code in your terminal:

   ```bash
   claude
   ```

2. Confirm Claude Code can actually reach your workspace. Ask it:

   > *"Using the LeanIX MCP server, what architecture decision templates are available in this workspace?"*

   Claude Code should call the MCP server and return at least the **Architecture Decision** template. If it returns an authentication or connection error, re-check the URL and token from Step 3 — the most common mistake is using `Bearer` instead of `Token`, or a trailing space in the pasted token.

> **What just happened:** Claude Code called a real tool (`get_architecture_templates`) in your live LeanIX workspace and read back the result. You are now driving LeanIX from your terminal.

## Step 5 — Create the Review-Standard ADR

Now create the Architecture Decision that captures InDAC's review standard.

Paste this prompt into Claude Code:

> *"Using the LeanIX MCP server, create an architecture decision titled 'Application Review — Top 20 Criteria Standard'. Set its status to Accepted. Populate it as follows:*
> - *Context: InDAC's architecture group has published a Top 20 Criteria standard — the universally applicable, immediately verifiable criteria used for portfolio rationalisation, M&A due diligence, and governance escalations. Every application review must now be assessed against this standard.*
> - *Decision: All application reviews at InDAC are evaluated against the Top 20 Criteria. Each criterion is assessed as Pass or Gap, with evidence. A review informs a keep / re-platform / retire recommendation.*
> - *Consequences: Reviews become comparable across the portfolio and traceable to an approved standard. Applications with unaddressed Gaps on gate criteria cannot be recommended for continued investment without a remediation plan.*
> *Set me as the approver, and set Last Reviewed to today. Then return the ADR's ID and URL."*

Claude Code will call `create_architecture_decision` and report back the new ADR's ID and URL.

## Step 6 — Confirm It Landed in LeanIX

1. Open LeanIX in your browser (the tab from Getting Started).
2. Navigate to **Architecture Decisions**.
3. Search for the decision title and open your ADR.
4. Confirm the **Context**, **Decision**, and **Consequences** sections match what you created — and that the status is **Accepted**.

> **This is the handoff.** You created this record from your terminal, and it is now a first-class object in the LeanIX workspace — visible in the UI, ready to be linked to fact sheets, and readable by the EA Assistant. From here on, you work inside LeanIX.

## Summary

You connected Claude Code to LeanIX over MCP, verified the connection against your live workspace, and created the review-standard ADR from the command line. The standard that was a PDF five minutes ago is now a governed, traceable Architecture Decision. In Exercise 2, you'll switch to the LeanIX EA Assistant and start exploring MaMa-CRM's landscape — the system you've been asked to put a verdict on.

[Back: Getting Started](../ex0/README.md) | [Next: Exercise 2 — Explore MaMa-CRM with the EA Assistant](../ex2/README.md)
