# Problem Brief - Week 1

Incident 01: Meridian Forge Robotics, MR-17 test cell.
Prepared by: Matthew
Course: CIT 140

---

## 1. Visible failure

According to Nia Voss, Night QA Supervisor, MR-17 started repeating Test K-44 at about 2:13 a.m., even though K-44 is no longer in use. The incident log supports her account. MR-17 accepted TEST_K44_START at 02:13:07 and started its repeat cycle at 02:13:09. At 02:14:02 the operator sent a stop request, and MR-17 answered with ACTIVE_INSTRUCTION_PENDING. MR-17 received the stop request, but the repeat cycle kept going and the test did not stop.

## 2. Evidence

- MR-17 accepted TEST_K44_START at 02:13:07. (Incident log, Nia Voss)
- The repeat cycle began at 02:13:09. (Incident log, Nia Voss)
- The operator stop request at 02:14:02 returned ACTIVE_INSTRUCTION_PENDING. (Incident log, Nia Voss)
- MR-17 has no active test assignment, and K-44 is not in the current test catalog. (Current scheduling console, Records Terminal)
- K-44 was marked retired 186 days before the incident and removed from the active workflow; the record does not confirm removal from every copy, service, or schedule. (Maintenance record, maintenance archive)
- The command was validly formatted and its source label is legacy_sync.exe; the telemetry does not identify the service owner or prove the broader cause. (Command telemetry, Elias Chen, Robotics Systems Engineer)
- Production is paused in the affected QA cell. (Staff statements, Mara Ilyan, Production Operations Manager)

## 3. System map

People: Nia Voss (Night QA Supervisor, keeps incident records); the operator who sent the stop request; Elias Chen (Robotics Systems Engineer, command telemetry); Mara Ilyan (Production Operations Manager).

Processes: test assignment through the current scheduler; test retirement through maintenance; the operator stop request; MR-17 finishing an active instruction before accepting a stop.

Information: incident log; current scheduler assignments and test catalog; maintenance archive; command telemetry; MR-17's full software history (not yet checked).

Technology: MR-17; the current scheduling console; an internal command interface; a service labeled legacy_sync.exe.

Rules: retired tests are removed from the active workflow; a stop request returns ACTIVE_INSTRUCTION_PENDING while an instruction is active.

Constraints: production in the QA cell is paused; a restart could clear information still needed for the investigation (Nia Voss, QA review); the owner and purpose of legacy_sync.exe are unverified; the full software history has not been reviewed.

## 4. Inside / outside boundary

Inside the system under investigation:
- MR-17 and how it accepts and completes commands
- The current scheduler and test catalog
- The K-44 retirement process and maintenance record
- legacy_sync.exe and the internal interface it used
- The operator stop request and its response

Outside it, but exerting force on it:
- Production operations and the pressure to resume work in the QA cell
- Staff proposals for restoring operation, which are out of scope for problem definition

Reason for the line: the investigation is about how a retired test reached MR-17 and why it could not be stopped, so everything that issues, holds, or blocks commands to MR-17 is inside. Production pressure affects urgency but does not explain the failure.

## 5. Impact

Confirmed: production is paused in the affected QA cell (Mara Ilyan). MR-17 ran a retired test in a repeat cycle, and an operator stop request did not halt it (Incident log).

Not yet confirmed: the scale of the impact, such as lost hours, units, or cost, was not reported. Whether other robots or schedules can also receive retired tests is unknown.

## 6. Problem statement

A test retired 186 days before the incident was still delivered to MR-17 by a source outside the current scheduler, labeled legacy_sync.exe, and once the test was running, an operator stop request could not interrupt it.

## 7. Next evidence-gathering step

Identify who owns legacy_sync.exe, why it is running, and whether it still holds Test K-44, by reviewing its service records alongside MR-17's full software history. This would show whether K-44's retirement left a copy that can still issue commands to MR-17, which the current records cannot confirm.
