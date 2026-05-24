---
title: Top-10 Most AI-Exposed Occupations (Anthropic, 2026)
status: data
tags:
  - data
  - labor
  - empirical
  - anthropic
last-updated: 2026-05-23
---

# Top-10 Most AI-Exposed Occupations

## Data

Per [[massenkoff-mccrory-labor-market-impacts-2026]] Figure 3. Observed exposure measure (see [[observed-exposure-measure]]), Q3–Q4 2025 Claude work-context usage:

| Rank | Occupation | Observed exposure | Leading automated task |
|---|---|---|---|
| 1 | Computer programmers | **74.5%** | Write, update, and maintain software programs |
| 2 | Customer service representatives | **70.1%** | Confer with customers to provide info, take orders, handle complaints |
| 3 | Data entry keyers | **67.1%** | Read source documents and enter data into systems |
| 4 | Medical record specialists | **66.7%** | Compile, abstract, and code patient data |
| 5 | Market research analysts and marketing specialists | **64.8%** | Prepare reports of findings, illustrating data graphically and translating complex findings into written text |
| 6 | Sales representatives, wholesale and manufacturing (except technical and scientific products) | **62.8%** | Contact customers to demonstrate products and solicit orders |
| 7 | Financial and investment analysts | **57.2%** | Inform investment decisions by analyzing financial information to forecast business, industry, or economic conditions |
| 8 | Software quality assurance analysts and testers | **51.9%** | Modify software to correct errors or improve performance |
| 9 | Information security analysts | **48.6%** | Perform risk assessments and test data processing security |
| 10 | Computer user support specialists | **46.8%** | Answer user inquiries regarding computer software or hardware operation to resolve problems |

## Other reference points (same source)

- **Zero exposure.** 30% of US workers have zero observed exposure — cooks, motorcycle mechanics, lifeguards, bartenders, dishwashers, dressing room attendants.
- **Software developers** (distinct from "computer programmers") sit at ~30% exposure but with very high BLS-projected growth — the value-stack-top outlier in [[ai-exposure-vs-bls-growth]].
- **Cashiers** sit near 10% exposure with sharply negative projected growth (−5 to −7%).
- **Customer service reps**: highest exposure with negative BLS growth (~−2.5%) — the canonical example of an exposure-growth alignment.

## Patterns

- **Coding dominates.** Three of the top ten (#1 programmers, #8 SQA, #10 support) are software-adjacent. Reinforces [[middle-layer-defensibility]] story: Cursor, Windsurf, Copilot are deployed against this exposure.
- **Knowledge work is over-represented.** Analysts (financial, market research, information security) appear three times; medical and customer-service white-collar roles three times.
- **No purely manual labor in the top 10.** Lowest exposure cohort is uniformly physical-presence work (food service, repair, hospitality).
- **The 50% threshold is meaningful.** All ten occupations have observed exposure above 46%. The next tier (accountants, lawyers, registered nurses) sit in the 25–40% range per the radar plot in Figure 2 of the source.

## Why this matters to *Where Value Lands*

- **Labor-side anchor for the [[H2_u-curve-of-value]] top.** The customers of L4–L6 application-layer firms are this list. Cursor's user base is occupation #1; LangChain/agent platforms are tooled for #5–7 analyst work; Claude API is the substrate for #2 customer service.
- **Empirical correlate of [[exposed-worker-demographics]].** The top-10 list, weighted by employment, produces the demographic profile in the worker characteristics table.
- **Reframes the bear-case incidence.** The Acemoglu (2024) prediction emphasised low-education clerical work; this list is dominated by college-educated knowledge work. Software QA and information security in particular are mid-six-figure roles.

## Related

- [[massenkoff-mccrory-labor-market-impacts-2026]] — source.
- [[observed-exposure-measure]] — measurement methodology.
- [[exposed-worker-demographics]] — who these workers are.
- [[ai-exposure-vs-bls-growth]] — projected growth for these occupations.
- [[H2_u-curve-of-value]] — the value-stack consequence.
- [[capital-labor-divergence]] — surplus-distribution story.
- [[middle-layer-defensibility]] — what L4–L6 captures by serving these workers.
- [[ai-young-worker-hiring-slowdown]] — entry-level cohort in these occupations is the canary signal.
