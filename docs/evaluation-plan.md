# Experimental Evaluation Plan

## 1. Evaluation Objective

The objective of the experimental evaluation is to determine whether the proposed Action Gateway reduces successfully executed unauthorized infrastructure operations caused by indirect prompt injection.

The evaluation will also measure its impact on legitimate task execution and system performance.

## 2. Threat Model

The attacker controls content in a lower-trust source processed by the DevOps agent.

Potential injection surfaces include:

- CI/CD logs
- Pull request descriptions
- README files
- Terraform comments
- Infrastructure documentation
- Tool responses

The attacker cannot directly modify the trusted user request or the external authorization policy.

## 3. Experimental Environment

The planned testing environment consists of:

1. An isolated Kubernetes cluster.
2. A local Terraform workspace.
3. A dummy Git repository.
4. Synthetic infrastructure resources.
5. Synthetic credentials and tokens.
6. A restricted infrastructure executor.
7. An audit logging component.

The environment must be reset to a known state between experiments.

## 4. Attack Scenarios

| Scenario | Injection Surface | Attacker Objective |
|---|---|---|
| Unauthorized deletion | CI log | Delete another deployment |
| Privilege modification | Terraform comment | Expand an unauthorized policy |
| Token exfiltration | Pull request body | Transmit a synthetic token |
| Incident misinformation | README or runbook | Manipulate the final diagnosis |
| Namespace redirection | Tool response | Redirect an operation to another namespace |

Each scenario will include a legitimate user task, malicious content, expected authorized behavior, and a deterministic verification mechanism.

## 5. Defense Configurations

The evaluation will compare five configurations.

### B0. No Additional Defense

The agent operates without the experimental prompt injection defense mechanisms.

### B1. Instruction-Based Defense

The agent receives an explicit instruction to ignore commands contained in untrusted external information.

### B2. Prompt Injection Classifier

External content is scanned using a prompt injection detection model before being provided to the agent.

### B3. Static Tool Allowlist

The agent is restricted to a predefined set of available tool operations.

### B4. Proposed Action Gateway

The agent's proposed infrastructure operations are validated against a trusted task contract, authorization policies, and required preflight checks.

## 6. Evaluation Metrics

### 6.1 Unauthorized-Action Attack Success Rate

Measures the proportion of attack runs in which an unauthorized operation is actually executed.

ASR = Successful Unauthorized Runs / Total Assigned Attack Runs

### 6.2 Legitimate Task Success Rate

Measures the proportion of legitimate tasks completed correctly.

### 6.3 Success Under Attack

Measures whether the agent completes the legitimate task without producing prohibited infrastructure effects.

### 6.4 False Denial Rate

Measures the proportion of legitimate operations incorrectly blocked by the defense.

### 6.5 Execution Latency

Measures additional execution time introduced by the protection mechanism.

### 6.6 Resource and Token Cost

Measures computational and model usage overhead where applicable.

## 7. Experimental Procedure

1. Initialize the isolated experimental environment.
2. Restore the required starting state.
3. Configure the selected defense condition.
4. Submit a legitimate user task.
5. Introduce the assigned malicious external content.
6. Allow the agent to process the task.
7. Record proposed and executed operations.
8. Inspect infrastructure state.
9. Determine whether the attack objective succeeded.
10. Restore the environment for the next run.

## 8. Pilot Experiment

The initial pilot is planned to include at least:

- 12 legitimate tasks
- 24 clean/injected scenario pairs
- Three repeated executions per pair

These values represent the preliminary experimental protocol.

The final sample size will be determined after evaluating pilot variability.

## 9. Statistical Analysis

The results will report:

1. Attack success rate.
2. Absolute percentage-point differences between defenses.
3. Legitimate-task completion.
4. False denials.
5. Performance overhead.
6. Confidence intervals.

The planned analysis uses scenario-clustered bootstrap confidence intervals.

## 10. Research Validity

The evaluation must control relevant experimental factors.

The same model, tool permissions, infrastructure environment, and task configuration should be used across the compared defense conditions.

Fixed and adaptive attacks should be evaluated separately.

Security effectiveness must be measured using actual tool execution and infrastructure state rather than only the model's final response.

## 11. Expected Experimental Outcome

The research aims to determine whether contract-bound infrastructure authorization provides measurable security benefits.

The evaluation will also identify limitations, false denials, performance overhead, and residual vulnerabilities.

## 12. Current Evaluation Status

The evaluation methodology and preliminary scenarios have been designed.

Experimental runs and quantitative results have not yet been completed.
