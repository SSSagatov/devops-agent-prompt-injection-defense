# Project Proposal

## 1. Project Title

Development and Experimental Evaluation of a Method for Protecting DevOps Agents Against Indirect Prompt Injection During Infrastructure Operations

## 2. Project Team

**University:** Astana IT University

**Team Members:**
- Sanzhar Sagatov
- Aiat Mergenbay

**Research Supervisor:** Kamila Tanyrbergenova

## 3. Problem Statement

Artificial intelligence agents are increasingly used to automate software development and infrastructure management tasks.

DevOps agents may interact with CI/CD pipelines, infrastructure configuration files, deployment logs, GitHub repositories, Kubernetes clusters, and Terraform environments.

During these operations, agents process information from sources that cannot always be trusted.

An attacker may insert malicious instructions into external content, including:

- README files
- Pull request descriptions
- CI/CD execution logs
- Infrastructure as Code comments
- Tool responses
- External technical documentation

When an AI agent interprets malicious content as an instruction rather than ordinary data, an indirect prompt injection vulnerability occurs.

Such attacks may cause an agent to:

1. Execute unauthorized infrastructure commands.
2. Modify or delete resources.
3. Expose confidential information.
4. Change infrastructure configurations.
5. Perform actions outside the original user's request.

Existing protection mechanisms include prompt injection detection, instruction hierarchy enforcement, tool restrictions, and policy-based authorization.

However, detecting suspicious text alone does not necessarily guarantee that an agent will execute only authorized infrastructure operations.

This project investigates a protection method that validates infrastructure operations before execution.

## 4. Research Objective

The objective of this research is to develop and experimentally evaluate a method for protecting DevOps agents against indirect prompt injection attacks during infrastructure operations.

The proposed method introduces a contract-bound Action Gateway that validates infrastructure operations against a trusted task contract and external security policies.

The protection mechanism aims to prevent unauthorized operations while maintaining the agent's ability to complete legitimate tasks.

## 5. Research Questions

### RQ1

How much does the proposed protection method reduce the rate of successfully executed unauthorized infrastructure operations compared with selected baseline defenses?

### RQ2

What impact does the proposed method have on legitimate-task completion, false denials, and execution latency?

### RQ3

Which attack surfaces and attacker objectives remain effective against the proposed protection mechanism?

## 6. Research Tasks

The project includes the following research and development tasks:

1. Analyze indirect prompt injection attacks against AI agents.
2. Review existing prompt injection defense mechanisms.
3. Define the threat model for DevOps agents.
4. Identify trusted and untrusted information sources.
5. Design a trusted task contract.
6. Develop the architecture of an Action Gateway.
7. Define authorization policies for infrastructure operations.
8. Create an isolated testing environment.
9. Prepare legitimate infrastructure tasks and injection scenarios.
10. Implement a prototype protection mechanism.
11. Conduct experimental comparisons with baseline defenses.
12. Evaluate security effectiveness and performance overhead.

## 7. Proposed Solution

The proposed solution uses an Action Gateway between the DevOps agent and infrastructure execution tools.

Before external information is processed, the system establishes a trusted task contract describing authorized operations and their scope.

When the agent requests an infrastructure operation, the gateway evaluates:

- Operation type
- Target resource
- Namespace or environment
- Trusted task contract
- External authorization policy
- Expected infrastructure changes

Operations that violate the trusted contract or security policy are denied.

The gateway records authorization decisions in an audit log.

This design aims to separate the agent's interpretation of external information from the authority required to execute infrastructure operations.

## 8. Expected Results

The expected outcomes include:

1. A formalized threat model for indirect prompt injection in DevOps environments.
2. A prototype of the proposed Action Gateway.
3. A set of reproducible attack scenarios.
4. An isolated infrastructure testing environment.
5. Experimental measurements of attack success and legitimate-task completion.
6. A comparison with existing defense approaches.
7. Recommendations for securing AI agents performing infrastructure operations.

These are planned outcomes and should not be interpreted as completed experimental results.

## 9. Project Scope

The research focuses on infrastructure operations involving Kubernetes, Terraform, and CI/CD systems.

The experimental environment will use isolated infrastructure and synthetic resources.

The project does not include:

- Production infrastructure access
- Real confidential credentials
- Unauthorized testing of third-party systems
- Automatic changes to live environments

## 10. Current Stage

The project is currently in the research and system design stage.

The problem statement, research objectives, related-work analysis, proposed architecture, functional requirements, and experimental evaluation plan have been prepared.

Implementation and experimental validation remain planned activities.
