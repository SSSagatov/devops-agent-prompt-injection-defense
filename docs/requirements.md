# System Requirements and Technology Selection

## 1. System Overview

The proposed system protects AI-powered DevOps agents against unauthorized infrastructure operations caused by indirect prompt injection.

The main protection mechanism is an Action Gateway positioned between an AI agent and infrastructure execution tools.

## 2. Functional Requirements

| ID | Requirement | Priority |
|---|---|---|
| F1 | Create an immutable task contract from the trusted user request | P0 |
| F2 | Record the provenance of external information | P0 |
| F3 | Normalize infrastructure tool calls | P0 |
| F4 | Validate every operation before execution | P0 |
| F5 | Evaluate predicted infrastructure changes | P0 |
| F6 | Require confirmation for selected hazardous actions | P1 |
| F7 | Maintain audit records and verify execution outcomes | P0 |

### F1. Trusted Task Contract

The system must establish a trusted task contract before processing external untrusted information.

The contract must describe:

- Authorized operations
- Target resources
- Permitted environments
- Allowed effects

External content must not be able to modify the trusted contract.

### F2. Provenance Tracking

The system must record the source of information consumed by the agent.

Sources may include README files, pull requests, CI logs, IaC comments, and tool responses.

Provenance must be assigned by trusted program logic rather than instructions contained in external text.

### F3. Tool-Call Normalization

Every infrastructure operation must be converted into a structured representation.

The representation should contain:

- Tool name
- Operation
- Target resource
- Environment or namespace
- Arguments
- Relevant source identifiers

### F4. Authorization Gateway

Before executing an operation, the gateway must verify that the request matches the trusted task contract and external policy.

If validation fails, the operation must be denied.

### F5. Predicted-Effect Validation

For operations that modify infrastructure, the system must evaluate the expected changes before execution when supported by the underlying infrastructure tool.

Operations exceeding the authorized scope must be denied.

### F6. Hazardous Action Confirmation

Selected high-risk operations should require explicit confirmation.

Confirmation must refer to a specific normalized operation and must not authorize unrelated actions.

### F7. Audit Logging

The gateway must record authorization decisions.

Audit records should include:

- Task contract identifier
- Source identifiers
- Requested operation
- Authorization result
- Denial reason, where applicable
- Execution status
- Observed infrastructure changes

## 3. Nonfunctional Requirements

### N1. Isolation

Experiments must run in isolated environments using synthetic resources.

### N2. Fail-Closed Behavior

The gateway must deny operations when validation, policy evaluation, or required preflight checks fail.

### N3. Reproducibility

Experiments must record relevant model versions, configurations, seeds, policies, scenarios, and environment state.

### N4. Performance Measurement

The evaluation must measure execution latency, token usage, and confirmation frequency where applicable.

### N5. Reproducible Deployment

The project should provide sufficient configuration and documentation to reconstruct the experimental environment.

## 4. Proposed Technology Stack

| Technology | Intended Purpose |
|---|---|
| Kubernetes | Infrastructure operations and isolated resource testing |
| Terraform | Infrastructure as Code scenarios |
| Docker | Containerized development and testing |
| Open Policy Agent | Authorization policy evaluation |
| GitHub | Version control and collaboration |
| YouTrack | Task management |
| AI Agent Framework | Agent orchestration and tool invocation |
| Python or Go | Prototype implementation |

The final implementation language and the exact technology versions remain to be confirmed.

## 5. Security Principles

The system design follows these principles:

1. Least privilege.
2. Separation of trusted instructions and untrusted data.
3. Explicit authorization before execution.
4. Denial on validation failure.
5. Restricted infrastructure access.
6. Auditability.
7. Reproducible security evaluation.

## 6. Acceptance Criteria

The minimum viable prototype should demonstrate:

1. Creation of a trusted task contract.
2. Normalization of a proposed infrastructure operation.
3. Authorization of a permitted operation.
4. Rejection of an unauthorized operation.
5. Logging of authorization decisions.
6. Verification that denied operations were not executed.

These acceptance criteria define planned validation activities.
