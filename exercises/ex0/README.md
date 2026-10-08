# Getting Started

## Overview

Before the exercises begin, log in to SAP LeanIX, orient yourself in the workspace, and find your participant number. Everything you need for the review of MaMa-CRM is already in this workspace.

**Duration:** 10 minutes

## Systems You Will Use

| System | Purpose |
|--------|---------|
| SAP LeanIX (shared workspace) | Where the review takes place — inventory, EA Assistant, and architecture decisions all live here |
| Claude Code (on your laptop) | Used briefly in Exercise 1 to talk to LeanIX over the MCP server |

## Step 1 — Log In to SAP LeanIX

1. Open your browser and navigate to the **SAP LeanIX URL** on your session card.
2. Sign in with the shared workspace credentials provided.
3. You should land on the SAP LeanIX home screen.

> **Tip:** The simplest way in is to log in with the shared account on your card, then — if you prefer your own login — use **Invite User** to add your SAP user. This avoids password-sharing friction for the rest of the session.

## Step 2 — Locate Your Participant Number

Your session card includes a **participant number** (for example, `P07`). Everyone in this session shares one workspace, so you will add your participant number to anything you create — starting with the Architecture Decision in Exercise 1 — to tell your work apart from everyone else's.

Write your participant number down somewhere handy. You will use it repeatedly.

## Step 3 — Orient Yourself in the Workspace

Spend two minutes finding the four places you will work today:

- **Inventory** — the catalogue of all applications, IT components, and other fact sheets in the landscape. This is where the **MaMa-CRM** application fact sheet lives.
- **Architecture Decisions** — where governance decisions (ADRs) are recorded. You will create one here in Exercise 1 and reference it throughout.
- **EA Assistant** — the conversational AI in SAP LeanIX, reached via **More** (top header) → **EA Assistant**. It is available throughout the session and does most of the analytical work from Exercise 2 onward.
- **Workspace Files (AI Assistants)** — admin area where documents are uploaded so the EA Assistant can reason over them. For this workshop, two documents are already uploaded and indexed:
  - `Application Review — Top 20 Criteria.pdf` — the standard you will review MaMa-CRM against
  - `mama-crm-arc42.pdf` — the architecture documentation for MaMa-CRM

> **Why this matters:** The EA Assistant can only reason over documents that have been indexed. Both documents above were indexed before the session, so the EA Assistant can already cite them — you do not need to upload anything.

## Step 4 — Take a First Look at MaMa-CRM

1. Open the **Inventory**.
2. Filter by **Application** type and open the **MaMa-CRM** fact sheet.
3. Skim it — lifecycle, business criticality, ownership, relations. Don't analyze it yet; just get a feel for what the Board is asking you to pass judgment on.

> **Do not change anything yet.** Exercise 1 starts in your terminal, with Claude Code.

## Summary

You are logged in, you know your participant number, and you have found the inventory, architecture decisions, the EA Assistant, and the indexed workspace files. In Exercise 1, you will connect Claude Code to this workspace and create the review standard as an Architecture Decision.

[Next: Exercise 1 — Create the Review Standard from Claude Code (via MCP)](../ex1/README.md)
