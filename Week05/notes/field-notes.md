# Week 5 Field Notes - Cedar Junction appointment process

One item per line. Source ID on every line. The Scope and Findings page cites
these IDs, so capture the ID exactly as the source shows it.

Lanes available in the starter: Visitor | Scheduling | Clinical Operations |
Intake | Next staff team

---

## Roles (the swimlanes)

| Lane / role | Person | What they own | Source ID |
|---|---|---|---|
| Visitor | the patient | requests the appointment, supplies details | W05-S01 |
| Scheduling | Mateo Silva, Appointment Scheduling Coordinator | booking, detail check, requesting readiness | W05-S01 |
| Clinical Operations |  |  |  |
| Intake | Dana Ruiz | receives the appointment at the desk |  |
| Next staff team |  |  |  |

## Process steps, in order

| # | Step | Lane | Source ID |
|---|---|---|---|
| 1 | Visitor requests an appointment, through the portal or a staff-assisted call | Visitor | W05-S01 |
| 2 | Record requested slot and support preferences | Scheduling | W05-S01 |
| 3 | Check the request for required booking details | Scheduling | W05-S01 |
| 4 | (no) Contact the visitor for clarification | Scheduling | W05-S01 |
| 5 | (no) Review the revised request, return to step 3 | Scheduling | W05-S01 |
| 6 | (yes) Request the clinical readiness decision | Scheduling -> Clinical Operations | W05-S01 |

## Decision points (diamonds)

| Decision | Branch A | Branch B | Source ID |
|---|---|---|---|
| Required booking details complete? | No -> contact visitor, review revised request, re-check | Yes -> request clinical readiness decision | W05-S01 |

## Handoffs (where work crosses a lane)

| From | To | What is handed over | Source ID |
|---|---|---|---|
| Scheduling | Clinical Operations | the request for a clinical readiness decision | W05-S01 |

## Exception paths

| Trigger | What happens now | Lane | Source ID |
|---|---|---|---|
| Required booking details missing | Contact the visitor, then review the revised request | Scheduling | W05-S01 |

---

## KEY FACTS TO CARRY (likely where the incident turns)

- [fact] The booking confirmation and the clinical readiness decision are two
  SEPARATE records. (W05-S01)
- [fact] A booking message records the requested time. It is NOT the clinical
  readiness record. (W05-S01)
- [fact] A held slot is still waiting for a readiness decision, so a held slot
  is not a confirmed appointment. (W05-S01)

Watch for a step later where someone treats a booking confirmation as if it
were a readiness decision. That is the shape of the gap this week.

---

## Path trace 1: the ORDINARY appointment

1. Visitor requests appointment (portal or staff-assisted call)
2. Scheduling records slot and support preferences
3. Details complete -> yes
4. Scheduling requests the clinical readiness decision
5. (continues in Clinical Operations)

## Path trace 2: the INCIDENT

(awaiting W05-S04)

Divergence point:
Where the model goes unclear:

## The gap (Scope and Findings page)

## What remains uncertain

---

## Raw capture log

### W05-S01 - Scheduling - Mateo Silva, Appointment Scheduling Coordinator

Interview:
- Handles appointment booking.
- Request arrives through the portal OR a staff-assisted call.
- Records requested time and support preferences, then checks the request.
- Missing details go back for clarification.
- A held slot is still waiting for a readiness decision.
- The booking confirmation and the readiness decision are separate records.

Source record (W05-S01):
- Start when a visitor requests an appointment.
- Record requested slot and support preferences.
- If required booking details are MISSING: contact the visitor and review the
  revised request.
- If details are COMPLETE: request the clinical readiness decision.
- A booking message records the requested time; it is not the clinical
  readiness record.

Instruction on the page: add the supported steps and decisions in the correct
role's lane. Mark uncertainty instead of inventing a missing action.

### W05-S02 - Clinical Operations
### W05-S03 - Intake
### W05-S04 - Record review
