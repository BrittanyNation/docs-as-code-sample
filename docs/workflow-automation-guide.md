# Workflow Automation Guide

This guide walks through automating a three-step approval process: a request is submitted, a manager approves or rejects it, and the requester is notified.

## Concepts
- **Process**: the full path a request travels.
- **Task**: one step a person or the system completes.
- **Gateway**: a decision point that routes the process based on data.

## Build the process
1. Create a new process and name it `Purchase Approval`.
2. Add a **Start** event and a user task named `Submit Request` with two fields: `Item` (text) and `Amount` (number).
3. Add a gateway named `Amount over $500?`.
   - If **yes**, route to a user task `Manager Approval`.
   - If **no**, route directly to the notification step.
4. Add a service task `Send Notification` that emails the requester the outcome.
5. Add an **End** event and connect every path to it.

## Test with sample data
| Case | Amount | Expected path |
|---|---|---|
| Small purchase | 120 | Skips manager approval |
| Large purchase | 940 | Requires manager approval |

## Verify
Deploy the process, submit both test cases, and confirm each one follows the path in the table above and the requester receives one notification per case.
