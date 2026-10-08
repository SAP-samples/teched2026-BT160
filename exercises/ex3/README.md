# Exercise 3 — Review MaMa-CRM Against the Standard

## Overview

This is the heart of the workshop. You will have the EA Assistant evaluate MaMa-CRM against the **Application Review — Top 20 Criteria**, drawing evidence from two authorized sources — the structured LeanIX inventory and the indexed arc42 architecture documentation — and produce an evidence table, a summary, and a gap register.

**Duration:** 25 minutes

## Background

A Board-grade review has three properties: it is **evidence-based** (every verdict points to a source), it is **conservative** (you don't claim a pass without proof), and it is **honest about uncertainty** (a self-attestation is weaker than independent verification). The prompt in this exercise builds those properties in.

Your sources are:

| # | Source | Where it lives |
|---|--------|----------------|
| 1 | The **Top 20 Criteria** standard | The ADR you created in Exercise 1 *and* the indexed `Application Review — Top 20 Criteria.pdf` in Workspace Files |
| 2 | The **MaMa-CRM inventory data** | The fact sheet and its related fact sheets (what you explored in Exercise 2) |
| 3 | The **arc42 architecture documentation** | The indexed `mama-crm-arc42.pdf` in Workspace Files |

> **Why two sources for the criteria?** You created the standard as a governed ADR in Exercise 1, and the full criteria PDF is also indexed. The EA Assistant can use either — the point is that the standard is *in the workspace*, not on someone's laptop, so the review is reproducible.

## Step 1 — Run the Assessment

Open (or stay in) the EA Assistant. Paste the following prompt. It is deliberately detailed — a Board review is one place where precision beats brevity.

> **Assessment: MaMa-CRM against the Top 20 Criteria**
>
> *Evaluate **MaMa-CRM** against the Application Review — Top 20 Criteria. Use only authorized sources: the Top 20 Criteria (from the Architecture Decision and the indexed criteria PDF), the MaMa-CRM fact sheet and its related fact sheets, and the indexed `mama-crm-arc42.pdf`. Do not use outside knowledge.*
>
> *For each of the 20 criteria, in order:*
> - *Find evidence in the arc42 PDF (record the section and heading) and in LeanIX (record the fact sheet, field, and value).*
> - *Assign a result: **Pass**, **Gap**, or **Conflict**. Gap is the default — a Pass requires explicit proof. If the two sources disagree, mark it **Conflict** and do not pass it.*
> - *Score confidence 1–10: proof from both sources = 9–10; one explicit source = 7–8; indirect or intent-only = 5–6; conflict or inference = 3–4; no evidence = 1–2. Flag anything ≤ 4 as low confidence.*
> - *For any security or compliance criterion, a self-attestation in the documentation caps confidence at 8; only independent verification reaches 9–10.*
>
> *Then produce:*
> - *An **evidence table**: Criterion | Domain | Result | Rationale (≤ 3 sentences, every claim attributed) | arc42 evidence (§ + heading) | LeanIX evidence (fact sheet · field · value) | Confidence.*
> - *A **summary**: counts of Pass / Gap / Conflict, average confidence, and the list of criteria scoring ≤ 4.*
> - *A **gap register**: the top gaps ranked by regulatory exposure → operational risk → technical debt → governance. For each: the gap, why it ranks there, the recommended action and the owner role that should take it, and whether an active initiative already exists in LeanIX.*

## Step 2 — Read Critically

The EA Assistant will produce a long, structured answer. Don't take it at face value — your job is to pressure-test it:

- **Spot-check two or three Passes.** Open the fact sheet or the cited arc42 section and confirm the evidence says what the Assistant claims.
- **Look hardest at the Conflicts.** A conflict between the arc42 doc and the inventory is often the most interesting finding — it means the documentation and the system of record disagree about reality.
- **Watch the confidence column.** A wall of 9s on a system "nobody fully owns" is a red flag that the Assistant is being too generous. Push back.

Use follow-up prompts to challenge it, for example:

> *"For criterion 4 (Technology Currency) you assigned a Pass. Show me the exact arc42 section and the LeanIX IT-component lifecycle values you based that on. If the component lifecycle is empty in LeanIX, downgrade the result."*

## Step 3 — Tie It to the Three-Way Decision

The Board does not want a scorecard — it wants a direction. Ask:

> *"Given this assessment, which Top 20 Criteria are the gate criteria that would block continued investment in MaMa-CRM as-is? Group the gaps into three buckets: those that argue for KEEP (fixable with data/governance work), those that argue for RE-PLATFORM (architecture or technology problems), and those that argue for RETIRE (the application should not continue). Be explicit about which bucket is heaviest."*

> **Why this matters — and why it shows off the Assistant:** This is where customization pays off. The EA Assistant is not giving you a generic CRM opinion — it is reasoning over *your* indexed arc42 document and *your* workspace's criteria to produce a recommendation specific to MaMa-CRM. Change the documents and the verdict changes with them.

## Summary

You have a defensible, criterion-by-criterion review of MaMa-CRM: an evidence table, a confidence-scored summary, a ranked gap register, and a first read on which way the keep / re-platform / retire decision leans. In Exercise 4, you will strengthen the weakest parts of this picture with live web research and a regulatory check before you finalize the verdict.

[Back: Exercise 2](../ex2/README.md) | [Next: Exercise 4 — Enrich with Web Research and Check EU AI Act Exposure](../ex4/README.md)
