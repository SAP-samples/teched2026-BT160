# Getting Started

## Overview

Before the exercises begin, prepare your laptop for Claude Code, log in to your SAP LeanIX workspace, and orient yourself. Everything you need for the review of MaMa-CRM is already in your workspace.

**Duration:** 10 minutes

## Systems You Will Use

| System | Purpose |
|--------|---------|
| SAP LeanIX (your own workspace) | Where the review takes place — inventory, EA Assistant, and architecture decisions all live here. You are the admin of your own workspace. |
| Claude Code (on your laptop) | Used briefly in Exercise 1 to talk to LeanIX over the MCP server |

## Step 1 — Prepare Your Laptop

Your session laptop needs a one-time setup so Claude Code can reach the internet through the venue's **hyperspace proxy**. **Do this before you open Claude Code or VS Code.**

1. Press the **Windows / Start** key.
2. Type **`bt160`**.
3. Under **Apps**, run **`LMU_BT160`** and let it finish.

![Searching for bt160 in the Start menu and running LMU_BT160](images/ex0_lmu_bt160.png)

> **Why this matters:** Without the proxy setup, Claude Code cannot authenticate or reach the LeanIX MCP server in Exercise 1. If `LMU_BT160` does not appear or the setup fails, raise your hand before continuing.

## Step 2 — Log In to Your SAP LeanIX Workspace

1. Open your browser and navigate to the **SAP LeanIX URL** on your session card. Each participant has their own workspace, so make sure you use *your* URL.
2. Sign in with the credentials provided on your card.
3. You should land on the SAP LeanIX home screen.

## Step 3 — Orient Yourself in the Workspace

Spend two minutes finding the four places you will work today:

- **Inventory** — the catalogue of all applications, IT components, and other fact sheets in the landscape. This is where the **MaMa-CRM** application fact sheet lives.
- **Architecture Decisions** — where governance decisions (ADRs) are recorded. You will create one here in Exercise 1 and reference it throughout.
- **EA Assistant** — the conversational AI in SAP LeanIX, reached via **More** (top header) → **EA Assistant**. It is available throughout the session and does most of the analytical work from Exercise 2 onward.
- **Workspace Files (AI Assistants)** — admin area where documents are uploaded so the EA Assistant can reason over them. For this workshop, two documents are already uploaded and indexed in your workspace:
  - `Application Review — Top 20 Criteria.pdf` — the standard you will review MaMa-CRM against
  - `mama-crm-arc42.pdf` — the architecture documentation for MaMa-CRM

> **Why this matters:** The EA Assistant can only reason over documents that have been indexed. Both documents above were indexed before the session, so the EA Assistant can already cite them — you do not need to upload anything.

## Step 4 — Take a First Look at MaMa-CRM

1. Open the **Inventory**.
2. Filter by **Application** type and open the **MaMa-CRM** fact sheet.
3. Skim it — lifecycle, business criticality, ownership, relations. Don't analyze it yet; just get a feel for what the Board is asking you to pass judgment on.

> **Do not change anything yet.** Exercise 1 starts in your terminal, with Claude Code.

## Summary

Your laptop is set up, you are logged in to your workspace, and you have found the inventory, architecture decisions, the EA Assistant, and the indexed workspace files. In Exercise 1, you will connect Claude Code to your workspace and create the review standard as an Architecture Decision.

[Next: Exercise 1 — Create the Review Standard from Claude Code (via MCP)](../ex1/README.md)
