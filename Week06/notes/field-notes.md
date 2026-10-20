# Week 6 Field Notes - Cedar Junction information routing

Source ID on every line. Page 3 cites these IDs.

---

## The four sources

| ID | Who / what | What it establishes |
|---|---|---|
| W06-S01 | System boundary and processing note | the boundary, the external teams, the four processes, the two stores |
| W06-S02 |  | the contract for the eight required fields |
| W06-S03 |  |  |
| W06-S04 | Delivery log | an export from D1 Report Register; the observed destination |

## External entities (page 1 boundary)

Anything that sends information in or receives information out, but is not
part of the system being modeled.

| External team / entity | Sends IN (label) | Receives OUT (label) | Source ID |
|---|---|---|---|
| Field Team | inspection report | validation note | W06-S01 |
| Electrical | - | routed work item | W06-S01 |
| Drainage | - | routed work item | W06-S01 |
| Structures | - | routed work item | W06-S01 |

## Inside vs outside scope (page 1)

System being modeled: the Inspection Report Routing System. [W06-S01]

Inside: receiving reports, checking the eight required fields, resolving the
destination from the routing table, sending the work item, and the two stores
D1 Report Register and D2 Routing Table. [W06-S01]

Outside: flight control, physical inspections, repair work, the Field Team
itself, the three receiving departments, and maintenance of the routing table
by the service administrator. [W06-S01]

Reason for the line: the system moves information about an inspection. It does
not fly the drone, perform the inspection, carry out the repair, or decide what
the routing table should contain. Those are outside. The administrator who
maintains D2 is explicitly outside the modeled boundary. [W06-S01]

## The four processes (page 2)

Numbered, verb + object. These are what the SYSTEM does, not what people do.

| # | Process | Input (from) | Output (to) | Source ID |
|---|---|---|---|---|
| 1 | Receive Report | inspection report (Field Team) | submitted report -> D1; received report -> P2 | W06-S01 |
| 2 | Check Required Fields | received report (P1); field contract (W06-S02) | validation note -> Field Team; accepted report -> P3; rejected report stops here | W06-S01 |
| 3 | Resolve Destination | accepted report (P2); routing entry (D2) | report with resolved destination -> P4 | W06-S01 |
| 4 | Send Work Item | report with resolved destination (P3) | work item -> resolved department; delivery record -> D1 | W06-S01 |

## The two data stores (page 2)

| Store | What it holds | Written by | Read by | Source ID |
|---|---|---|---|---|
| D1 Report Register | submitted reports and delivery records | P1 Receive Report, P4 Send Work Item | the delivery log in W06-S04 is an export from it | W06-S01 |
| D2 Routing Table | routing entries | the service administrator, OUTSIDE the boundary | P3 Resolve Destination | W06-S01 |

## The eight data fields (page 3) - ALL EIGHT REQUIRED

| # | Field name | Definition | Format / values | Source ID |
|---|---|---|---|---|
| 1 |  |  |  |  |
| 2 |  |  |  |  |
| 3 |  |  |  |  |
| 4 |  |  |  |  |
| 5 |  |  |  |  |
| 6 |  |  |  |  |
| 7 |  |  |  |  |
| 8 |  |  |  |  |

## The finding: expected vs observed destination

Report traced (ID):
Expected destination (and the record that says so):
Observed destination (and the record that says so):
What the mismatch shows:
What the records do NOT establish:

## One unanswered question

---

## Raw capture log

### W06-S01 - System boundary and processing note

- Boundary = the Inspection Report Routing System.
- Field Team supplies inspection reports and receives validation notes.
- Electrical, Drainage and Structures receive routed work items.
- OUTSIDE: flight control, physical inspections, repair work.

P1 Receive Report
- accepts the Field Team's inspection report
- writes a submitted report to D1 Report Register
- passes the received report to P2

P2 Check Required Fields
- checks the eight required fields against the contract in W06-S02
- sends a validation note to the Field Team
- passes an accepted report to P3
- a REJECTED report does not continue to routing

P3 Resolve Destination
- reads routing entries from D2 Routing Table
- passes a report with its resolved destination to P4
- a service administrator maintains the table OUTSIDE the modeled boundary;
  table maintenance is not part of this case

P4 Send Work Item
- sends a work item to the resolved department
- writes a delivery record to D1 Report Register
- the delivery log in W06-S04 is an export from that register

INSTRUCTION (quoted close to verbatim): model the route supported by the log;
show the policy discrepancy in the FINDING, not as an already completed repair.
-> So there is a policy discrepancy coming. Draw what actually happened, and
   put the discrepancy on page 3 as the finding. Do not draw the fix.
### W06-S02 -
### W06-S03 -
### W06-S04 -
