
# Task 2 Test Cases

## Test Case List

| Test ID | Requirement ID | Test Scenario | Expected Result | Risk |

| TC-01 | FR-02 | An authenticated operator with the correct role issues a valid command. | The system accepts the command and 

proceeds with execution. | High |

| TC-02 | FR-02 | An unauthenticated user issues a robot command. | The system rejects the command and records the security event.

| Critical |

| TC-03 | FR-02 | An authenticated operator without the required role issues a command. | The system rejects the command and does not 

execute it. | Critical |

| TC-04 | FR-02, FR-10 | A valid command is received, authenticated, authorised, executed, and followed by a status report. | The 

correct status is reported and the command and relevant events are logged. | High |

| TC-05 | SAF-02 | Battery capacity falls below the emergency level. | The robot enters Safe Mode within 3 seconds of detecting the 

condition. | Critical |

| TC-06 | SAF-02 | Chamber or battery temperature exceeds the critical threshold. | The robot enters Safe Mode within 3 seconds of 

detecting the condition. | Critical |

| TC-07 | NFR-02 | Connect 20 robots simultaneously and exchange status information. | The system supports all 20 connected robots 

and their communication. | High |

| TC-08 | NFR-02 | Connect multiple robots and verify that each robot's status and identity are handled separately. | Status 

information is associated with the correct robot, without mixing robot identities. | High |

| TC-09 | FR-10 | Execute a valid command and inspect the event log. | The log contains the relevant command, robot ID, timestamp, 

and event or state change. | High |

| TC-10 | SAF-02 | Measure the time between detecting a critical battery or temperature condition and entering Safe Mode. | The 

measured response time is no more than 3 seconds. | Critical |

## Command Processing Test Sequence

For TC-01 and TC-04, verify the applicable stages:

1. The command is received.

2. The operator is authenticated.

3. The operator's role is checked.

4. The command is accepted and executed.

5. The robot's status is reported.

6. The command and relevant events are logged.

For TC-02 and TC-03, verify that rejected commands are not executed.

## Regression Testing

After CR-01, rerun TC-05, TC-06, and TC-10.

After CR-02, rerun TC-07 and TC-08.

After CR-03, rerun TC-01, TC-02, TC-03, TC-04, and TC-09.

Record the actual result, pass/fail status, and evidence when each test is executed. The expected results above are test criteria, not claims that the tests have already passed.
