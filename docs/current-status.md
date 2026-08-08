# Current Status

## Public release posture

This repository is ready to function as a public-facing documentation harness.

What is already in place:
- a static site shell with docs routing
- a cleaned architecture narrative
- explicit methodology and policy pages
- a bounded demo plan
- release notes for public review

## What the public repo can honestly claim

- the architecture is designed around exact evidence and review states
- the system abstains when evidence is insufficient
- ambiguous relations are meant to pass through human review
- the public site explains the system without exposing private material

## What is operational in the underlying ecosystem

The private LexCon / LexO stack is organized around:
- acquisition from approved public sources
- retrieval with IndexO and sentence-index
- curation in legal-reviewer
- promotion through review-graph
- canonicalization in graph-legal-ir
- grounded reasoning in LexO
- constrained public surfaces in LexCon-hub and related apps

## What is stable enough to show publicly

| Area | Status | Public implication |
|---|---|---|
| Architecture narrative | Stable | Can be reviewed externally |
| Evidence-first methodology | Stable | Safe to describe and reuse |
| Release policy | Stable | Makes the boundary explicit |
| Demo interactive prototype | Built | `demo.html` implements all 6 criteria from public-demo-plan.md |
| Public site shell | Stable | Ready for GitHub and portfolio use |

## What remains intentionally private

- raw vault contents
- unreviewed relation queues
- internal prompt stacks
- lab-only scratch work
- any material that would confuse a public reader about what is actually shipped

## Honest limits

This repository does not claim:
- full legal coverage
- autonomous legal advice
- final product completeness
- public exposure of the operational corpus

It does claim:
- explainability
- traceability
- abstention on weak evidence
- a serious release posture
