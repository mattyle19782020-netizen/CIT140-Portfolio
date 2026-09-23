# Week 2 Field Notes

One item per line. Source ID on every line. The report must cite at least two.

## Figure classification (measured / estimated / unknown)

| Figure | Value | Source ID | Class | Why |
|---|---|---|---|---|
| Planning envelope, cost ceiling | $3,000 internal staff time | W02-S01 | measured | Stated by the sponsor as the limit; it is a given constraint, not a projection |
| Planning envelope, time ceiling | 10 business days | W02-S01 | measured | Same |
| Retrieval requests during first assessment | 6 | W02-S02 | measured | Counted by Nia Voss; individual times in the source |
| Staff time for those retrievals | 60 staff minutes total (10 min average) | W02-S02 | measured | Counted by Nia Voss |
| Retrievals returning both an owner and a clear link to source | 2 of 6 | W02-S02 | measured | Counted by Nia Voss |
| Robot downtime | not recorded | W02-S02 | unknown | Nia states these are retrieval records only, not downtime |
| Lost sales / production loss | not recorded | W02-S02 | unknown | Nia states these are retrieval records only, not lost sales |
| Time a later change would save | none | W02-S02 | unknown | Record states no measured estimate exists |
| "Review will cut retrieval time in half" | n/a | none | unsupported benefit claim | Confirmed in evidence check; must not appear in the report |
| Staffing hours (all four lines) | 48 h total | W02-S04 | estimated | Record calls them provisional; require confirmation after authorization |
| Elapsed duration | 8 business days | W02-S04 | estimated | Proposed, and conditional on exports by day 3 |
| Implied blended rate if 48 h must fit $3,000 | about $62.50/h | derived from W02-S01 + W02-S04 | estimated | My arithmetic, not a stated figure; check against W02-S05 before using |
| Export access approval date | not set | W02-S04 | unknown | Requested, not confirmed; if denied, revise or defer |

Class definitions:
- measured: recorded in a record, verifiable
- estimated: someone's projection, not yet observed
- unknown: not established by any record

## Limits from the packet (W02-S04)

| Limit | Stated value | Source ID |
|---|---|---|
| Planning envelope, cost | Up to $3,000 of internal staff time | W02-S01 |
| Planning envelope, duration | Ten business days | W02-S01 |
| Nature of the envelope | Limits for evaluating the proposal, not approved funding. A proposal outside them must be revised or returned to the sponsor | W02-S01 |
| Tooling | Existing tools can support the review | W02-S04 |
| Read-only export access | Requested, not confirmed | W02-S04 |
| Staff hours | Provisional; normal duties continue; availability must be confirmed before authorization | W02-S04 |
| Staffing, analyst | 24 h across days 1-8 | W02-S04 |
| Staffing, engineering | 12 h, no earlier than day 4 | W02-S04 |
| Staffing, QA | 8 h during days 5-7 | W02-S04 |
| Staffing, Operations | 4 h across days 1 and 8 | W02-S04 |
| Total staff effort | 48 hours (sum of the four lines above) | W02-S04 | 
| Proposed elapsed duration | 8 business days, assumes exports arrive by day 3 and tasks overlap | W02-S04 |
| Safety boundary | All work outside the safety glass; read-only copies; originals preserved; no permission to operate equipment | W02-S04 |

## Scope in / out (W02-S03)

Current workflow (not replaced by this request): QA requests a record; the relevant custodian locates it; QA and Engineering check its origin and meaning; Operations receives a summary. The request does not replace this workflow with a new system.

Included (W02-S03):
- Review command-authorization ownership for the affected cell
- Inventory the controls used to schedule and retire its tests
- Document an evidence-preservation checklist
- Identify gaps and hand off a report for later decisions

Deliverables (W02-S03), three:
1. One command-ownership record
2. One scheduling/retirement control inventory
3. One evidence-preservation checklist
Unknown owners or missing evidence are recorded explicitly, not filled in with guesses.

Excluded (W02-S03):
- Restarting or operating MR-17
- Changing software or schedules
- Deleting or modifying original records
- Buying a replacement robot
- Selecting a vendor
- Extending the review to other cells

Note: the analyst may recommend a smaller review or another decision. Any scope change must explain what value is retained or deferred (W02-S03).

## Success measures (W02-S05)

- Candidate measure, built on the W02-S02 baseline: after the review, repeat the same retrieval exercise and compare (a) total staff minutes for six requests, baseline 60, and (b) how many requests return both an owner and a clear link to source, baseline 2 of 6.
- Nia's instruction: keep the baseline, propose a sensible way to check improvement, and tell the sponsor what still needs measuring (W02-S02).

## Value claims to test (not yet quantified)

- Traceable record for QA and Engineering to investigate from (W02-S01), no figure attached.
- Defensible basis for Operations to request later work (W02-S01), no figure attached.
- Explicitly NOT a promise of restored production (W02-S01). Do not convert this into savings.

## Assumptions and open questions

1. [unknown] Future savings from the review: not measured (W02-S02). No savings figure may be claimed.
2. [unknown] Robot downtime and production loss for this cell: not recorded in any record so far.
3. [open question, carried from Week 1] What issued TEST_K44_START, and who owns legacy_sync.exe? Cause is not established.

## Carried forward from Week 1

- The source of TEST_K44_START is unverified; legacy_sync.exe owner and purpose unknown.
- A restart could clear evidence still needed (Nia Voss, Week 1 QA review).
- Impact scale (hours, units, cost) was never quantified in Week 1.

## Visit log

### 1. Mara Ilyan, Operations call

W02-S01, Request for a bounded review (Mara Ilyan, Production Operations Manager):
- Proposes a QA Control Review of the affected QA cell.
- Three things it would establish: who owns command authorization; how retired tests remain controlled; how evidence will be preserved for later decisions.
- Sponsor needs a Business Case Recommendation: proceed, revise, defer or decline, with reasons and conditions. Mara carries it to the sponsor.
- Neither the request nor the report authorizes work or expenditure.
- Expected value: a traceable record QA and Engineering can investigate from, and a defensible basis for Operations to request later work.
- A completed review is not a promise of restored production.
- Planning envelope: up to $3,000 of internal staff time over ten business days. Limits for evaluation, not funding. Outside them means revise or return to sponsor.

Q1: What decision do you need from me?
- A recommendation she can take to the sponsor: proceed, revise, wait for missing information (defer), or decline, with reasons.
- Neither Mara nor the analyst approves spending here.

Q2: What would this review actually improve?
- QA and Engineering get records they can trace.
- Operations gets a sound reason to request any later work.
- Useful "even before we know the technical cause" (Mara's words; matches Week 1, where the command source is still unverified).
- "I can't promise this review will put the robot back into production." No production-restoration benefit may be claimed.

### 2. Nia Voss, QA observation

W02-S02, Evidence-retrieval workload:
Q: What have you actually measured?
- Six retrieval requests took sixty staff minutes altogether (10 min average).
- Only two of the six came back with both an owner and a clear link to the original source.
- Her caution: "Those are retrieval records for this cell, not robot downtime or lost sales."
- Individual times: 8, 10, 12, 9, 11, 10 minutes = 60 total, average 10.
- Some requests overlapped, so 60 staff minutes is not 60 minutes of elapsed time.
- Record instruction: do NOT add these minutes to the project estimate; that estimate covers future work.
- Four of six required follow-up to establish a custodian, a source link, or both.
- No measured estimate exists of how much time a later change would save.
- "Preserving evidence and finding its owner are useful even if the robot's technical fault has not been identified." (W02-S02)
Q: Can we say the review will save money?
- No. Future savings have not been measured; nothing in these records supports a savings claim.
- Keep the baseline, propose a way to check improvement, tell the sponsor what still needs measuring.
- Do not turn 60 minutes into a company-wide loss.

- Read: 4 of 6 retrievals could not be tied to an owner and a source. That gap is evidence for the review's stated purpose (command authorization ownership, evidence preservation) and must not be converted into a savings figure.

### 3. Records, QA records workstation

W02-S03, Proposed scope and current workflow (Mara Ilyan with Nia Voss, review draft):
- Scope bounded to one QA cell; matches the three goals in W02-S01 (authorization ownership, retired-test control, evidence preservation).
- Three deliverables, all documents. No change to any system is included.
- Exclusions are broad and deliberate: no restart, no software or schedule changes, no record deletion, no purchase, no vendor selection, no other cells.
- The review does not replace the existing request-and-custodian workflow.
- Gaps stay visible by design, which fits Week 1 leaving the command source unverified.

### 4. Elias Chen, Engineering

W02-S04, Capacity, access and operating limits:
Q: Do we have what we need to do the review?
- Existing tools can support the review.
- Read-only exports: access REQUESTED, not confirmed. Unresolved dependency.
- Staff hours are provisional; people keep their normal duties.
- Availability must be confirmed before the work is authorized.
- Implication: any schedule built on the W02-S05 estimate assumes approvals and hours not yet in place.

W02-S04 record detail:
- Uses read-only record exports and existing documentation tools.
- Access requested, not confirmed. "If access is denied, the team must revise the work or defer it." (W02-S04)
- Provisional staffing: analyst 24 h (days 1-8); engineering 12 h (no earlier than day 4); QA 8 h (days 5-7); Operations 4 h (days 1 and 8). Total 48 staff hours. Confirmation required after authorization.
- Proposed elapsed duration 8 business days, assuming exports arrive by day 3 and tasks overlap. Against the 10-day envelope in W02-S01, that leaves 2 days of slack.
- "Staff effort hours and elapsed business days measure different things." Do not conflate 48 hours with 8 days.
- Risks, not established delays: a shift reassignment could remove the QA window; late exports could delay Engineering. Neither has occurred in this packet.
- Safety: all work outside the safety glass, originals preserved, read-only copies, missing access recorded. A recommendation does not grant permission to operate equipment.

### 5. Operations review (QA review desk / Operations call)
