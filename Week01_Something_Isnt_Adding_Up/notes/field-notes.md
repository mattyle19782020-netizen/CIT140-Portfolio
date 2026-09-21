# R4 / R5 Field Notes

Not a separate Canvas submission this week, but it is what makes the brief
defensible. One item per line. Source on every line.

## Statement classification (R4: at least 3 correct)

Classify what each record says before you believe it.

| # | Statement (short) | Source | Class | Why |
|---|---|---|---|---|
| 1 | MR-17 accepted TEST_K44_START at 02:13:07 | Incident log (Nia Voss) | fact | Directly recorded in the log (confirmed in Command Nexus evidence check) |
| 2 | "We don't use that test anymore" (K-44 is retired) | Nia Voss, interview; Maintenance record | fact | Now supported: Maintenance record marks K-44 retired 186 days before the incident |
| 3 | MR-17 was behaving normally before the incident | Nia Voss, interview | assumption | Limited to what she personally saw; she says it must be checked against the logs |
| 4 | Who or what issued TEST_K44_START | Incident log (Nia Voss) | open question | Log records the acceptance, not the origin of the command |
| 5 | Production has paused in the affected QA cell | Staff statements (Mara Ilyan) | fact | Staff record establishes what Mara reported; cite Mara. Independent check would need production records |
| 7 | Another scheduling service assigned K-44 to MR-17 | Current scheduler (Records Terminal) | assumption | Possible explanation; records do not establish it (confirmed in evidence check) |
| 8 | Who owns legacy_sync.exe and why it is running | Elias Chen, command telemetry | open question | Elias has not verified owner or purpose |
| 6 | A controlled restart may clear the active state | Staff statements (Elias) | assumption | Unverified explanation. Also a remedy, so it stays out of the brief |

Class definitions (Command Nexus labels):
- fact: the source directly supports it
- assumption: an explanation not yet verified
- open question: something you still need to find out

## Supported facts (R4: at least 3, one per line, with sources)

1. [fact] 02:13:07, MR-17 accepted TEST_K44_START. (source: Incident log, Nia Voss, Night QA Supervisor)
2. [fact] 02:13:09, the repeat cycle began. (source: Incident log, Nia Voss)
3. [fact] 02:14:02, the operator stop request returned ACTIVE_INSTRUCTION_PENDING. (source: Incident log, Nia Voss)
4. [fact] The stop request was received but did not halt the test; MR-17 kept repeating K-44. (source: Nia Voss interview, consistent with Incident log 02:14:02)
5. [fact] Mara Ilyan, Production Operations Manager, reports production has paused in the affected QA cell. (source: Staff statements, Mara Ilyan)
6. [fact] The current scheduler shows MR-17 has no active test assignment. (source: Current scheduler, current scheduling console, Records Terminal)
7. [fact] Test K-44 does not appear in the current test catalog. (source: Current scheduler, current scheduling console, Records Terminal)
8. [fact] K-44 was marked retired 186 days before the incident and removed from the active workflow. (source: Maintenance record, Records Terminal)
9. [fact] The maintenance record does not confirm K-44 was removed from every copy, service, or schedule. (source: Maintenance record, Records Terminal)
10. [fact] The command was in a format MR-17 accepts and came through an internal interface with source label legacy_sync.exe. (source: Elias Chen, Robotics Systems Engineer, command telemetry)
11. [fact] Mara Ilyan, Production Operations Manager, states production is paused in the affected QA cell; the full software history has not yet been checked. (source: Mara Ilyan, operations call)

## Contradictions and gaps

Where two records disagree, log both sides. This is usually where the real
problem is.

| Claim A (source) | Claim B (source) | What would settle it |
|---|---|---|
| K-44 retired 186 days ago, removed from active workflow (Maintenance record; Nia) | MR-17 accepted TEST_K44_START (Incident log) | Test catalog or change record showing K-44's status and whether it was removed from MR-17 |
| Current scheduler: no active assignment for MR-17; K-44 not in catalog (Records Terminal) | MR-17 accepted TEST_K44_START at 02:13:07 (Incident log) | Identify what issued the command: logs from any other scheduling service or copy with access to MR-17 |
| MR-17 behaved normally before 02:13 (Nia) | Not yet checked against any log | Records / lab terminal history for MR-17 before 02:13:07 |

## Assumptions and open questions (R5: at least 2)

1. [open question] K-44 is retired per the maintenance record, but does any copy, service, or schedule still hold it? (Maintenance record does not confirm full removal)
2. [assumption] MR-17 had no earlier problems before 02:13 (Nia Voss, limited to what she saw).
3. [open question] What issued TEST_K44_START at 02:13:07, and why did MR-17 accept it?
5. [assumption] Another scheduling service assigned K-44 to MR-17 (Records Terminal evidence check; not established).
6. [open question] Who owns legacy_sync.exe, why is it running, and does it still hold K-44? (Elias Chen: not verified)
7. [open question] What does the full software history for MR-17 show? (Mara Ilyan: still needs to be checked)
4. [open question] Why does a stop request not override an active instruction (ACTIVE_INSTRUCTION_PENDING)?

## Raw capture log

Timestamped notes as you visit each source. Keep it messy, clean it up later.

### 1. Nia Voss, Night QA Supervisor (QA observation)

Q: What happened?
- About 2:13 a.m. MR-17 began repeating Test K-44. Nia: "we don't use that test anymore."
- Operator sent a stop request. MR-17 received it but said its current instruction had to finish. Kept repeating.
- Pointed to the incident log for command and response times.
- Incident log: 02:13:07 accepted TEST_K44_START / 02:13:09 repeat cycle began / 02:14:02 stop request returned ACTIVE_INSTRUCTION_PENDING.
- Stop request came 53 seconds after the repeat cycle began.

Q: Was it behaving normally before this?
- "As far as I saw, yes." That is what she reported.
- She can only speak for what she saw. Says her account should be compared with the logs before claiming there were no earlier problems.

Evidence panel, Staff statements (Mara Ilyan, Production Operations Manager):
- Nia reports MR-17 behaved normally before the incident.
- Elias says a controlled restart may clear the active state. (assumption; remedy, keep out of brief)
- Mara confirms production has paused in the affected QA cell.

Source confirmed as Maintenance record (Records Terminal): K-44 retired 186 days before the incident; removed from the active workflow; not confirmed removed from every copy, service, or schedule.

### 2. Records, lab terminal

Record: What is MR-17 assigned to do? (Current scheduler, current scheduling console)
- MR-17 has no active test assignment.
- K-44 does not appear in the current test catalog.
- Record only shows what this scheduler shows, not what every other service may be doing.

Record: What does "retired" mean in this record? (Maintenance record)
- K-44 marked retired 186 days before the incident.
- Removed from the active workflow.
- Does not confirm removal from every copy, service, or schedule.

### 3. Elias Chen, Robotics Systems Engineer (command telemetry)

Q: What does the command tell us?
- Command was in a format MR-17 accepts.
- Came through an internal interface. Source label: legacy_sync.exe.
- He has not verified who owns that service or why it is running.
- Something to follow up on; he cannot say it explains the whole incident.

### 4. Mara Ilyan, Production Operations Manager (remote operations call)

Q: How is the work affected?
- Production paused in the affected QA cell.
- She needs the work running safely again (goal, not evidence; keep remedy out of brief).
- Can help with the operating schedule.
- Full software history still needs to be checked.
- No scale figures given (units, hours, cost). Impact scale is unconfirmed.

### 5. QA review
