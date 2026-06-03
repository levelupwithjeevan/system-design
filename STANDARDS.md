# Handbook Standards

Every chapter must follow this template exactly and pass the Principal Review gate before it is considered complete.

## Chapter Template

1. `# Chapter NN — <Title>`
2. `TL;DR —` one paragraph a busy Staff engineer would want.
3. `## Mental model` — core idea in plain language + one SIMPLE Mermaid diagram.
4. `## How it works` — mechanism + one INTERMEDIATE Mermaid diagram (sequence/flow).
5. `## Design Review Lens` — answer each, briefly and concretely:
   - What problem is this actually solving?
   - What assumptions does it depend on (and when do they break)?
   - What breaks FIRST at 10x scale?
   - What breaks FIRST at 100x scale?
   - How would Netflix vs Amazon vs a 5-person startup each approach this differently, and why?
6. `## Variants / approaches` — the real options in a table: strengths and costs of each.
7. `## Worked example (with capacity model)` — a concrete scenario. MUST include, with all assumptions stated and the arithmetic shown: QPS estimate, storage estimate, network/bandwidth estimate, peak-vs-average traffic, and a growth projection. State assumptions explicitly; never present a number without its basis.
8. `## Failure Walkthrough` — describe system behavior AND recovery for each:
   - single node failure
   - network partition
   - full regional failure
   - critical dependency outage
   - data corruption / poison data
   For each: what the user sees, how the system detects it, how it recovers, and the RPO/RTO implication where relevant.
9. `## Decision Framework` — a Mermaid decision tree (flowchart) for "given these conditions, which approach?" For pure-concept chapters with no design choice, give a smaller "when to reach for this" tree instead.
10. `## Tradeoffs & alternatives` — for the main recommendation answer all four explicitly: WHY use it / what it COSTS / ALTERNATIVES / WHEN NOT to use it.
11. `## Staff & Principal lens` — beyond the technical tradeoff, discuss: organizational impact, operational burden (who carries the pager), team ownership boundaries, cost governance, long-term maintainability, and migration complexity.
12. `## Interview answer vs production reality` — three short parts: what interviewers expect to hear; what actually happens in production; and the common simplifications that are fine in an interview but wrong in prod.
13. `## Common pitfalls & misconceptions` — what people get wrong, in interviews and in prod.
14. `## Interview questions` — tiered Mid / Senior / Staff / Principal, each with a MODEL answer. Staff/Principal answers must engage org impact, ops burden, cost, and migration — not just deeper tech.
15. `## Connections` — Prerequisites (chapters to read first), Related chapters, and Builds toward (what later chapters depend on this). Link by chapter number/title from `SYLLABUS.md`.
16. `## Further reading` — primary sources only (papers, official docs). No content-farm blogs.

## Principal Review Gate

A chapter is not done until every answer is YES. Fix every failure before moving on.

- Is every technical claim accurate, and is every empirical claim cited or labeled a heuristic?
- Is it production-realistic — would it survive a Fortune-100 environment and hyperscale traffic?
- Is anything oversimplified in a way that's actively misleading (vs. an acknowledged simplification)?
- Does the capacity model show its assumptions and math, with no unsourced numbers?
- Are all 16 sections present, substantive, and free of TODOs/filler?
- Are there >=2 valid Mermaid diagrams plus the Decision Framework tree?
- Is the "when NOT to use it" specific, and do the Staff/Principal sections address org/ops/cost?
- Would any part confuse a careful 3-5 year reader? If so, rewrite it.

After the gate, briefly note to the reviewer which checks almost failed and what changed.

## Chapter Workflow

1. Create exactly one chapter folder for the next approved chapter.
2. Write `README.md` using the exact template above.
3. Check canonical terms against `STYLE_GUIDE.md`.
4. Validate Mermaid diagrams.
5. Run the Principal Review gate and revise until every check is YES.
6. Commit as `chapter NN: <title>`.
7. Stop and wait for the reviewer to say `continue`.

