# Prox — Decision Records

Product and architecture decision records from building **[Prox](https://www.proxdesign.co)**, a production RAG-based AI discovery platform, from zero to public GA (July 2026) as a solo founder.

> **Provenance.** Prox is built via AI-assisted development — Claude writes most of the code. These records document the part that isn't delegable: what to build, which models and vendors to use, what the quality bar is, and when to ship. Each record is a sanitized public version of a decision that lives in the production repo and its Linear workspace; internal specifics (file paths, prompt text, unreleased features) are removed, outcomes and reasoning are not.

## Why publish decision records

A resume line says *what* happened ("cut search turns from 6 to 2"). A decision record shows *how the call was made* — the constraint, the alternatives priced, the reversal plan, and what actually happened afterward, including the decisions that went against my own work. For an AI product role, this is the artifact that matters: the code is increasingly generated, but the decisions are the job.

## Index

| # | Decision | The one-line version |
|---|---|---|
| [001](decisions/001-llm-judge-selection-and-lock.md) | LLM-as-judge model selection & reproducibility lock | The newer, more capable model disagreed with itself 17% of the time — so the judge is the older model, pinned and frozen |
| [002](decisions/002-keyword-to-semantic-retrieval.md) | Keyword → semantic retrieval migration | Embeddings + pgvector cut median search turns from 6 to 2; keyword demoted to fallback, not deleted |
| [003](decisions/003-precommitted-ship-hold-gates.md) | Pre-committed ship/hold gates as release governance | Write the decision rule before the experiment; it HELD my own redesign, and that's the point |
| [004](decisions/004-build-vs-buy-evaluation-funnel.md) | Build-vs-buy through a formal evaluation funnel | Capability probes never authorize a ship; formal evals do — vendors and models go through the same funnel as features |
| [005](decisions/005-paid-tier-reversible-golive.md) | Paid tier go-live as a single reversible switch | Allowlist-gated Stripe rollout, checkout-to-entitlement validated at $0, GA was one flag |
| [006](decisions/006-multi-tenant-data-security-bar.md) | The multi-tenant data-security bar | Tenant isolation, consent (GPC/DNT), right-to-erasure — behind a 10-assertion gate every release passes |
| [007](decisions/007-model-routing-shadow-first.md) | Model routing: investigate fully, ship nothing (yet) | Production is single-tier by design; the cascade is specified, the eval judge is the calibration oracle, and it ships only when the numbers say so |

## Format

Standard ADR shape — Status / Context / Decision / Consequences — plus a **What happened** section wherever the outcome is already known. Records are immutable once accepted; a reversal is a new record, not an edit.

---

*Dave Pollack · [LinkedIn](https://www.linkedin.com/in/dave-pollack) · [github.com/D-Pollack](https://github.com/D-Pollack)*
