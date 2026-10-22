# Protecting DevOps Agents Against Indirect Prompt Injection

## Project Information

**Full Title:** Development and Experimental Evaluation of a Method for Protecting DevOps Agents Against Indirect Prompt Injection During Infrastructure Operations

**University:** Astana IT University

**Team Members:**
- Sanzhar Sagatov
- Aiat Mergenbay

**Research Supervisor:** Kamila Tanyrbergenova

## Problem Statement

AI-powered DevOps agents interact with external information such as CI/CD logs, GitHub pull requests, README files, infrastructure configurations, and tool responses. Attackers may insert malicious instructions into these lower-trust sources and cause an agent to perform infrastructure operations that were not authorized by the user.

## Research Objective

The objective of this project is to develop and experimentally evaluate a method that prevents instructions from lower-trust content from causing unauthorized infrastructure actions while preserving the successful execution of legitimate tasks.

## Proposed Solution

The proposed method uses a contract-bound Action Gateway between an AI agent and infrastructure tools.

The gateway evaluates proposed operations against:
1. A trusted user task contract.
2. External authorization policies.
3. The operation's normalized arguments and target resources.
4. A predicted infrastructure change, where applicable.

Unauthorized operations are denied and logged.

## Research Questions

- RQ1: How much does the method reduce actually executed unauthorized actions compared with baseline defenses?
- RQ2: What is the impact on legitimate-task success, false denials, and latency?
- RQ3: Which attack surfaces and attacker objectives remain successful?

## Planned Technologies

- Kubernetes
- Terraform
- Open Policy Agent (OPA)
- AI agent with restricted tool access
- Docker and isolated testing environments
- GitHub and YouTrack

Technology selection and implementation scope remain subject to validation.

## Current Status

The research proposal, literature review, requirements, proposed architecture, example API interactions, and experimental evaluation plan have been prepared.

A working security gateway and experimental measurements are not yet reported.

## Documentation

- [Project Proposal](docs/proposal.md)
- [Literature Review](docs/literature-review.md)
- [Existing Solutions](docs/existing-solutions.md)
- [Requirements](docs/requirements.md)
- [Architecture](docs/architecture.md)
- [Experimental Evaluation Plan](docs/evaluation-plan.md)
- [Project Status](docs/project-status.md)

## Next Steps

1. Validate the scope and requirements with the research supervisor.
2. Implement a restricted infrastructure-operation testbed.
3. Develop the contract-bound Action Gateway.
4. Create clean and injected test scenarios.
5. Run reproducible experiments and compare defense baselines.

## Research Ethics and Safety

All security testing will be performed in isolated environments using synthetic resources and credentials. No production infrastructure or real secrets will be used.
