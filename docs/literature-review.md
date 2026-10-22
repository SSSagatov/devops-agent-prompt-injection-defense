# Literature Review

## 1. Introduction

Indirect prompt injection is a security vulnerability in which malicious instructions are embedded in lower-trust content consumed by a large language model application or AI agent.

Unlike direct prompt injection, the attacker does not necessarily control the user's original request.

Instead, the attacker manipulates external information such as documents, webpages, logs, repositories, or tool responses.

For DevOps agents, this vulnerability is particularly significant because agents may have access to infrastructure management tools.

An injected instruction could influence the agent to perform an unauthorized operation.

## 2. Indirect Prompt Injection Research

### 2.1 Abdelnabi et al. (2023)

"Not What You've Signed Up For" investigates indirect prompt injection attacks against LLM-integrated applications.

The study demonstrates how attacker-controlled external content can influence applications that process untrusted information.

This work establishes the fundamental trust-boundary problem addressed by our research.

### 2.2 InjecAgent (2024)

InjecAgent introduces a benchmark for evaluating indirect prompt injection attacks against tool-integrated language model agents.

It provides examples of attacker objectives and injection methods.

Our research uses this work to inform the classification of attack scenarios.

### 2.3 AgentDojo (2024)

AgentDojo provides a dynamic environment for evaluating attacks and defenses involving autonomous agents.

It emphasizes realistic agent tasks and measurable attack outcomes.

Our evaluation methodology draws on its approach to stateful task execution and reproducible experiments.

### 2.4 Agent Security Bench (2025)

Agent Security Bench investigates security vulnerabilities across different stages of AI agent execution.

The benchmark provides a structured approach to analyzing attack surfaces and defense effectiveness.

## 3. Detection-Based Defenses

### 3.1 Task Shield (2025)

Task Shield examines whether agent operations align with the legitimate user task.

This approach is relevant because indirect prompt injection attempts often redirect an agent away from its original objective.

### 3.2 MELON (2025)

MELON investigates a defense approach based on repeated execution and behavioral comparison.

The work is relevant to the evaluation of detection effectiveness and computational overhead.

## 4. Authorization and Control-Based Defenses

### 4.1 ShieldAgent (2025)

ShieldAgent explores verifiable safety policy reasoning for AI agents.

Its policy-based approach is relevant to the proposed Action Gateway.

### 4.2 IPIGuard (2025)

IPIGuard uses a tool dependency graph to defend against indirect prompt injection.

Its approach demonstrates how relationships between tool calls can help constrain agent execution.

### 4.3 DRIFT (2025)

DRIFT investigates dynamic rule-based defenses and injection isolation.

The work provides useful context for separating trusted execution decisions from untrusted information.

### 4.4 CaMeL (2026)

CaMeL proposes an architectural approach to preventing prompt injection by separating trusted control flow from untrusted data.

It is one of the primary architectural references for this project.

### 4.5 Progent (2026)

Progent investigates privilege control for AI agents.

The work is relevant to restricting tool operations and their arguments according to predefined authorization rules.

## 5. Infrastructure-Specific Research

### 5.1 NetInjectBench (2026)

NetInjectBench investigates indirect prompt injection attacks involving agents performing network operations.

It demonstrates the importance of evaluating attacks in operational environments rather than only general-purpose assistant tasks.

### 5.2 Containing the Autonomous Operator (2026)

This research examines security mechanisms for AI agents operating in Kubernetes environments.

It provides infrastructure-specific context for defense-in-depth architectures.

### 5.3 GitInject (2026)

GitInject investigates prompt injection attacks in AI-powered CI/CD pipelines.

This work is relevant to our threat model because CI/CD files and execution logs are potential sources of attacker-controlled instructions.

## 6. Research Gap

Existing studies investigate prompt injection detection, agent behavior, tool restrictions, and policy enforcement.

However, these approaches do not fully establish the effectiveness of combining trusted task contracts, infrastructure-specific authorization, and predicted-effect verification within a common DevOps experimental environment.

Our research focuses on this combination.

The proposed mechanism checks whether an infrastructure operation is authorized by the original task rather than relying exclusively on whether its surrounding text appears malicious.

## 7. Research Contribution

The intended contribution is the design and experimental evaluation of a contract-bound authorization mechanism for infrastructure-operating AI agents.

The evaluation will investigate:

1. Prevention of unauthorized infrastructure changes.
2. Successful completion of legitimate tasks.
3. False authorization denials.
4. Runtime performance overhead.
5. Residual vulnerabilities under fixed and adaptive attacks.

## 8. References

The complete bibliography is available in [References](../research/references.md).
