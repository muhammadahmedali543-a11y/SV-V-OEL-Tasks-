
# Task 2 Requirements Traceability Matrix (RTM)

## Purpose

This matrix connects the changed requirements to system behaviour, operational constraints, test cases, and risk levels.

## Traceability Matrix

| Requirement ID | State ID | Transition ID | Operation ID | Constraint ID | Test Case ID | Risk Level |

| SAF-02 | S-01, S-05 | T-01 | OP-06 | C-01 | TC-05, TC-06, TC-10 | Critical |

| NFR-02 | S-07 | T-06 | OP-07 | C-02 | TC-07, TC-08 | High |

| FR-02 | S-02, S-03, S-06 | T-02, T-03 | OP-01, OP-02 | C-03 | TC-01, TC-02, TC-03 | Critical |

| FR-02 | S-03, S-04 | T-04 | OP-03 | C-03 | TC-01, TC-04 | High |

| FR-10 | S-04 | T-05 | OP-04, OP-05 | C-04 | TC-04, TC-09 | High |

## State Definitions

| State ID | State Name | Description |

| S-01 | IDLE | The robot is waiting for a valid request. |

| S-02 | COMMAND_RECEIVED | A command has been received and is awaiting validation. |

| S-03 | COMMAND_AUTHORISED | The operator is authenticated and has permission to issue the command. |

| S-04 | COMMAND_EXECUTED | An authorised command has been executed. |

| S-05 | SAFE_MODE | The robot is in its defined safe operating mode. |

| S-06 | COMMAND_REJECTED | A command has been rejected because authentication or authorisation failed. |

| S-07 | CONNECTED | A robot is connected to the control system. |

## Transition Definitions

| Transition ID | From State | To State | Condition |

| T-01 | S-01 | S-05 | A critical battery or temperature condition is detected. |

| T-02 | S-02 | S-03 | Authentication and role authorisation succeed. |

| T-03 | S-02 | S-06 | Authentication or role authorisation fails. |

| T-04 | S-03 | S-04 | The authorised command is accepted for execution. |

| T-05 | S-04 | S-04 | Execution status and relevant event information are reported and logged. |

| T-06 | S-07 | S-07 | A connected robot exchanges communication with the control system. |

## Operation Definitions

| Operation ID | Operation |

| OP-01 | Authenticate the operator. |

| OP-02 | Check the operator's role and permissions. |

| OP-03 | Execute an accepted command. |

| OP-04 | Report the robot's status. |

| OP-05 | Log commands and relevant events with robot ID and timestamp. |

| OP-06 | Monitor critical battery and temperature conditions and initiate Safe Mode. |

| OP-07 | Manage simultaneous robot connections and communication. |

## Constraint Definitions

| Constraint ID | Constraint |

| C-01 | Safe Mode must be entered within 3 seconds after detection of a specified critical battery or temperature condition. |

| C-02 | The system must support at least 20 simultaneously connected robots. |

| C-03 | A robot command may be accepted only after successful authentication and role authorisation. |

| C-04 | Relevant command and event records must include a robot ID and timestamp. |

## Change Request Traceability
 
| Change Request | Requirement | Main Verification | Regression Tests |

| CR-01 | SAF-02 | Timed battery and temperature fault-injection tests | TC-05, TC-06, TC-10 |

| CR-02 | NFR-02 | Simultaneous connection and communication test | TC-07, TC-08 |

| CR-03 | FR-02 | Authentication and role-authorisation tests | TC-01, TC-02, TC-03, TC-04, TC-09 |

## Traceability Notes

Requirement IDs refer to the affected requirements from Task 1.

State, transition, operation, and constraint IDs must remain consistent with the models and verification work in the later tasks.

Test cases define expected outcomes. Actual execution results must be recorded separately.

Risk levels indicate the potential impact of failure and should be reviewed against the project's risk analysis.
