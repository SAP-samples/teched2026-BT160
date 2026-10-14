# Exercise 4 — Enrich with Web Research and Check EU AI Act Exposure

## Overview

Your review so far is built entirely from internal sources. Two of the Board's questions need more than that. First, the **re-platform / retire** decision needs an outside view: is MaMa-CRM's technology stack a dead end, and what would replace it? Second, governance needs to know whether MaMa-CRM carries any **EU AI Act** exposure. In this exercise you use the EA Assistant's web-research and EU AI Act capabilities to close both gaps.

**Duration:** 20 minutes

## Part A — Web Research: Is the Stack a Dead End?

MaMa-CRM runs on Java, Oracle, and the Drools rule engine, with persistence generated from a UML model and DSLs for its data formats. The arc42 documentation tells you *what* the stack is. The web tells you whether that stack is a liability in 2026.

### Step 1 — Research Technology Currency

**➤ Ask the EA Assistant:**

> *"Using web research, assess the current support and end-of-life status of MaMa-CRM's core technologies: the Java runtime, Oracle Database, and the Drools rule engine. For each, note the latest supported versions and any end-of-support dates that would make a current deployment a risk. Cite your sources."*

Compare what you learn to criterion 4 (Technology Currency) from Exercise 3. Does the web view strengthen a gap you already found, or soften it?

### Step 2 — Scope the Alternatives

If the leaning is toward re-platform or retire, the Board will ask "replace it with what?"

**➤ Ask the EA Assistant:**

> *"Using web research, identify two or three credible options for a mass-market, multi-mandator CRM / customer-communication platform that could replace a self-built system like MaMa-CRM — including at least one SAP option. For each, give a one-line fit summary against MaMa-CRM's core need: onboarding a new mandator or campaign without changing code."*

> [!NOTE]
> **Why this matters:** A retire or re-platform recommendation without a credible successor is not actionable. The EA Assistant's web research lets you attach real options to the recommendation — the difference between "this is a problem" and "here is the path."

## Part B — EU AI Act: Is There Regulatory Exposure?

Governance reviews increasingly have to answer a compliance question up front: does this application fall under the EU AI Act, and if so, at what risk level?

> [!NOTE]
> **About the EU AI Act extension:** The EU AI Act classification capability is an optional extension for SAP LeanIX. It must be activated under **Administration → Optional Features and Early Access** before use. In this workshop your workspace already has it enabled. If you want to use this in your own workspace after the session, see [EU AI Act Classification in the EA Assistant](https://help.sap.com/docs/LEANIX/72d375467c1e4dcb872dfa2998b6328d/d4ca4b50141d4cdfb0122915e2b91f25.html) for setup instructions.

### Step 3 — Classify MaMa-CRM

**➤ Ask the EA Assistant:**

> *"Classify MaMa-CRM against the EU AI Act. Based on the fact sheet and the arc42 documentation, does this application include AI systems in the meaning of the Act? If so, what risk category applies and why? If it does not, state that explicitly and explain the basis for excluding it."*

MaMa-CRM is a classic rule-engine-driven CRM, not a machine-learning system — so a well-reasoned **"out of scope / minimal risk"** answer is a perfectly good result. The value is in having the determination **on the record**, with a rationale, rather than leaving it as an open question for an auditor to raise later.

> [!NOTE]
> **Why this matters:** A clean negative is still a governance artifact. "We checked, and here is why it does not apply" is exactly what an audit wants to see — and it is produced here in one prompt, grounded in your own documentation.

### Step 4 — Record the Determination in the Fact Sheet

The EU AI Act classification is more useful on the record than in a chat reply.

**➤ Ask the EA Assistant:**

> *"Update the MaMa-CRM application fact sheet with the EU AI Act classification we just established. Set the EU AI Act risk category to the value from your assessment, and add a brief one-sentence rationale in the notes field. Confirm the update and return the field values you set."*

After the EA Assistant confirms the update, open the MaMa-CRM fact sheet in the LeanIX UI and check the **EU AI Act** section to verify the values landed correctly.

> [!NOTE]
> **Governance note:** While you are on the fact sheet, look at the **Last Updated** field or open the change history. You will see your name — not "EA Assistant" — as the author of the change. LeanIX records every update under the authenticated user who triggered it, regardless of whether a human or an AI assistant made the edit. AI does the work; you own the record. This is what human-in-the-loop governance looks like in a system built for AI-assisted workflows.

### Step 5 — Fold Both Into the Picture

**➤ Ask the EA Assistant:**

> *"Add the technology-currency web findings and the EU AI Act determination to the gap register from the earlier assessment. Re-rank the gaps if the new evidence changes their severity, and note any gap where an external source now gives us higher confidence than internal data alone did."*

## Summary

Your review now combines internal evidence with an outside view of the technology stack, a shortlist of credible successors, and a recorded EU AI Act determination. You have everything you need to make the call. In Exercise 5, you will synthesize it into the keep / re-platform / retire verdict and prepare your shareback.

[Back: Exercise 3](../ex3/README.md) | [Next: Exercise 5 — Deliver the Verdict](../ex5/README.md)
