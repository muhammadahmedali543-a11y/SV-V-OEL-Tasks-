
# Task 2 Change Log

## Change Request 

| CR ID | Requirement ID | Change Description | Status |

| CR-01 | SAF-02 | Make Safe Mode trigger conditions and response time measurable. | Modified |

| CR-02 | NFR-02 | Specify the minimum number of simultaneously connected robots. | Modified |

| CR-03 | FR-02 | Require both authentication and role-based authorisation. | Modified |

## CR-01: Safe Mode Response

**Requirement ID:** SAF-02 

**Status:** Modified

**Old Requirement:**

The robot shall enter Safe Mode when a critical battery or thermal condition is detected.

**New Requirement:**

The robot shall enter Safe Mode within 3 seconds when chamber or battery temperature exceeds the critical threshold or battery 

capacity falls below the emergency level.

**Reason for Change:**

The original requirement does not specify a response time or exact trigger conditions. The revised requirement defines a 3-second 

time limit and identifies the temperature and battery conditions that trigger Safe Mode.

**Why It Is More Testable:**

A tester can simulate the specified temperature and battery conditions, measure the time until Safe Mode is entered, and verify that 

the response occurs within 3 seconds.

## CR-02: Simultaneous Robot Connections

**Requirement ID:** NFR-02  

**Status:** Modified

**Old Requirement:**

The system shall support communication with multiple robots simultaneously.

**New Requirement:**

The system shall support at least 20 simultaneously connected robots.

**Reason for Change:**

The original requirement does not define how many robots the system must support. The revised requirement provides a minimum capacity target.

**Why It Is More Testable:**

A tester can connect 20 robots simultaneously and verify that the system supports their connections and communication.

## CR-03: Command Authentication and Authorisation

**Requirement ID:** FR-02  

**Status:** Modified

**Old Requirement:**

Only authenticated operators shall be permitted to issue robot commands.

**New Requirement:**

The system shall require authenticated and role-authorised operators before accepting any robot command.

**Reason for Change:**

The original requirement mentions authentication but does not explicitly require checking whether an operator's role permits the 

requested command. The revised requirement includes both checks.

**Why It Is More Testable:**

A tester can submit commands using an unauthenticated user, an authenticated user with an unauthorised role, and an authenticated 

user with an authorised role. The system should reject the first two and accept the permitted command from the third.

## Regression Testing After Changes

|Change Request| Tests to Re-run | Reason |

|CR-01         |TC-05,TC-06,TC-10|Verify battery and temperature triggers and the 3-second Safe Mode limit.|

|CR-02         |TC-07,TC-08      | Verify simultaneous robot connections and communication at the required capacity.|

|CR-03         |TC-01,TC-02,TC-03,TC-04,TC-09| Verify authentication, role authorisation, command execution, status reporting, and 

event logging.
