<!-- SPDX-FileCopyrightText: 2026 SAP SE or an SAP affiliate company and teched2026-BT160 contributors -->
<!-- SPDX-License-Identifier: Apache-2.0 -->

# SAP LeanIX solutions: Govern with Enterprise Architecture Assistant and MCP

[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/teched2026-BT160)](https://api.reuse.software/info/github.com/SAP-samples/teched2026-BT160)

## Session Overview

Build AI-native capabilities directly within the SAP LeanIX solutions ecosystem. Using MCP server for SAP LeanIX solutions and Enterprise Architecture Assistant, connect AI agents and assistants to your architecture data and obtain skills that surface enterprise architecture insights. Make your architecture repository accessible to AI tooling.

Every enterprise runs a long tail of self-built applications that never got the scrutiny the ERP backbone did. Sooner or later, someone has to decide what to do with them — and the decision has to be defensible.

This workshop puts you in that seat. Working with **SAP LeanIX**, you will review a business-critical, self-built application against a formal review standard, gather evidence from structured inventory data and architecture documentation, enrich it with live web research, check it for regulatory exposure, and deliver a **keep / re-platform / retire** verdict to the Board.

You will do this using two surfaces onto the same workspace:

- The **MCP server**, which lets an AI coding assistant (**Claude Code**) create and read LeanIX data from your terminal.
- The **EA Assistant**, the conversational AI built into SAP LeanIX, which does the analytical heavy lifting inside the UI.

> A short introduction to SAP LeanIX, the EA Assistant, and the MCP server will be presented at the start of the session.

## About SAP LeanIX

**SAP LeanIX** is SAP's enterprise architecture management platform. It gives EA and IT governance teams a single place to maintain the inventory of all applications, technologies, and data in their organization, track their lifecycles, and connect the architecture landscape to business capabilities and strategy.

Two capabilities are central to this workshop:

- The **EA Assistant** is a conversational AI solution inside SAP LeanIX. It researches and analyzes your enterprise architecture data in natural language — reading fact sheets, traversing relations, reasoning over documents you have made available to it, and performing live web research.
- The **MCP server** exposes your LeanIX workspace — fact sheets, architecture decisions, inventory search — as tools that any Model Context Protocol client (such as Claude Code) can call. It is the bridge between your own developer toolchain and your governed architecture data.

## Business Scenario

**InDAC** is a mid-sized data center that runs business-process outsourcing for mass-market clients — insurance, telecommunications, energy, and credit-card providers. Its flagship platform, **MaMa-CRM**, was built in-house to absorb a new client (a "mandator") or campaign *without changing code*. Seven to ten developers, built on Java, Oracle, and the Drools rule engine, it has grown over the years into the system the whole business runs on.

It is also the system nobody fully owns anymore. The team that built it has shrunk, the documentation has drifted, and the architecture decisions behind it live in people's heads — not on paper.

Last quarter, **you** — John, senior enterprise architect at InDAC — presented the new **Application Review — Top 20 Criteria** standard to the architecture group. This quarter, the **Board of Directors** has lost confidence in the group running MaMa-CRM and wants it reviewed against that standard — with evidence — before deciding whether to **keep, re-platform, or retire** it. Jack, the CIO, just put it on your desk.

> You have the LeanIX workspace, the MaMa-CRM fact sheet, its arc42 architecture documentation, and the review criteria. What you *don't* have yet is a written architecture decision capturing the standard — so that is where you start. By the end of the session you will hand the Board a defensible verdict.

## What You Will Learn

- How to connect **Claude Code** to a LeanIX workspace through the **MCP server**, and create a governed Architecture Decision Record from your terminal
- How to use the **EA Assistant** to explore an application and its landscape in natural language — lifecycle, ownership, dependencies, and business-capability coverage
- How to run an **evidence-based application review** in which the EA Assistant reasons over indexed architecture documentation and a workspace review standard
- How to **enrich** your analysis with live web research and check an application for **EU AI Act** exposure
- How to synthesize everything into a **keep / re-platform / retire** recommendation ready for a Board shareback

## Session Structure

| # | Exercise | Surface | Duration |
|---|----------|---------|----------|
| GS | [Getting Started](exercises/ex0/README.md) | Prepare your laptop, connect Claude Code to your workspace via MCP, log in to SAP LeanIX, and orient yourself | Setup | 15 min |
| 1 | [Create the Review Standard from Claude Code (via MCP)](exercises/ex1/README.md) | Use Claude Code (already connected) to explore MaMa-CRM and create the review-standard ADR | Claude Code → LeanIX | 20 min |
| 2 | [Explore MaMa-CRM with the EA Assistant](exercises/ex2/README.md) | Use the EA Assistant to map the application and its landscape | LeanIX UI | 25 min |
| 3 | [Review MaMa-CRM Against the Standard](exercises/ex3/README.md) | Produce an evidence table and gap register against the Top 20 Criteria | LeanIX UI | 25 min |
| 4 | [Enrich with Web Research and Check EU AI Act Exposure](exercises/ex4/README.md) | Research alternatives and classify regulatory exposure | LeanIX UI | 20 min |
| 5 | [Deliver the Verdict](exercises/ex5/README.md) | Synthesize a keep / re-platform / retire recommendation and share back | LeanIX UI | 15 min |

**Total exercise time: ~115 minutes**

## Requirements

- Access to **your own SAP LeanIX** workspace (URL, credentials, and MCP token provided on your session card) — each participant gets a dedicated workspace in which they are the admin
- **Claude Code** — pre-installed on your session laptop (used briefly in Exercise 1)
- A modern web browser (Chrome or Edge recommended)
- No prior experience with SAP LeanIX, the EA Assistant, or MCP required

## System Access

| System | URL | Credentials |
|--------|-----|-------------|
| SAP LeanIX | *(your workspace URL — on session card)* | *(on session card)* |
| LeanIX MCP server | *(your workspace MCP endpoint — on session card)* | Browser OAuth login (set up in Getting Started) |

## Exercises

- [Getting Started](exercises/ex0/README.md)
- [Exercise 1 - Create the Review Standard from Claude Code (via MCP)](exercises/ex1/README.md)
- [Exercise 2 - Explore MaMa-CRM with the EA Assistant](exercises/ex2/README.md)
- [Exercise 3 - Review MaMa-CRM Against the Standard](exercises/ex3/README.md)
- [Exercise 4 - Enrich with Web Research and Check EU AI Act Exposure](exercises/ex4/README.md)
- [Exercise 5 - Deliver the Verdict](exercises/ex5/README.md)

## Related Sessions

This workshop sits in the **Accelerate and Derisk Your AI-Native Transformation** subtrack. The following sessions deepen the context.

| Session | Type | Title |
|---------|------|-------|
| BT161 | Hands-on Workshop | From Discovery to Decommissioning: A Hands-On AI Governance Workshop |
| BT100 | Deep Dive | Make architecture data collection faster, easier, and more reliable with AI |
| ST101 | Strategy Talk | Navigating AI-native enterprise architecture with SAP LeanIX solutions |
| BT800 | Road Map | SAP LeanIX solutions road map for AI-native enterprise architecture |

## Further Resources

- [SAP LeanIX — Connecting to the MCP Server](https://help.sap.com/docs/leanix/ea/connecting-to-mcp-server)
- [SAP LeanIX — Setting up the EA Assistant](https://help.sap.com/docs/leanix/ea/setting-up-enterprise-architecture-assistant)
- [SAP LeanIX AI Plugins and Agent Skills](https://github.com/SAP/leanix-ai-plugins)
- [EU AI Act — Official Text](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689)
- [Sample Documents](sampleDocuments/) — the arc42 architecture documentation and Top 20 Criteria PDF used in this workshop; download and upload to your own workspace to run the same review pattern against your own applications

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## Contributing

Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct

Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## License

Copyright 2026 SAP SE or an SAP affiliate company and teched2026-BT160 contributors. Please see our [LICENSE](LICENSE) for copyright and license information. Detailed information including third-party components and their licensing/copyright information is available [via the REUSE tool](https://api.reuse.software/info/github.com/SAP-samples/teched2026-BT160).
