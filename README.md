# Credit Risk Review Agent

An agentic workflow for credit risk review: from loan documentation to a client-ready credit review line sheet, quality-checked and rated, with a human-in-the-loop review gate.

## Planned architecture

The system is built as three cooperating agent stages:

1. **Credit storyline agent**: reads the underlying credit documents (borrower financials, facility terms, covenants, collateral, prior reviews) and drafts the credit storyline: the borrower, the request, the risk drivers and the mitigants.
2. **Deliverable and rating agent**: turns the storyline into a client deliverable, a credit risk review line sheet, runs its own QA and QC pass, and proposes a final credit rating based on the assessed documents.
3. **Human-in-the-loop QA/QC agent**: independently checks the line sheet against the supporting credit documents, flags unsupported statements or figures, and routes the output to a human reviewer before release.

Each stage keeps its inputs and outputs traceable back to source documents, so every rating and statement can be audited.

## Status

Early stage. The repository is set up; agent implementation, prompt and evaluation work, and fine-tuning will be developed here.

## Principles

- Source-grounded: every figure and claim should trace to a supporting document.
- Human in the loop: no rating or deliverable is released without reviewer sign-off.
- Auditable: prompts, versions and evaluation results are tracked in git.

## Repository layout

Planned layout, to be filled in as the work progresses:

```
agents/        agent definitions (storyline, deliverable and rating, QA/QC)
prompts/       versioned prompts
evals/         evaluation sets and results
docs/          design notes and decisions
```
