# Comparison of Existing Prompt Injection Defense Solutions

## 1. Overview

This document compares existing technologies used to detect or mitigate prompt injection attacks in AI applications and agents.

The systems considered are:

1. Microsoft Prompt Shields
2. Google Model Armor
3. AWS Bedrock Guardrails
4. NVIDIA NeMo Guardrails
5. Meta LlamaFirewall

The comparison focuses on their documented capabilities and suitability for protecting DevOps agents.

## 2. Evaluation Criteria

The following criteria are used:

- K1: Indirect prompt injection detection
- K2: Tool-response inspection
- K3: Outbound tool-call checking
- K4: Ability to block unsafe operations
- K5: Configurable security rules
- K6: Deployment options
- K7: Audit and monitoring capabilities
- K8: Infrastructure-specific authorization based on resource and expected effect

## 3. Comparison Table

| Solution | Injection Detection | Tool-Response Inspection | Tool-Call Controls | Infrastructure-Specific Authorization |
|---|---|---|---|---|
| Microsoft Prompt Shields | Yes | Supported integrations | Risk-based intervention | Not established |
| Google Model Armor | Yes | Supported MCP integrations | Content assessment | Not established |
| AWS Bedrock Guardrails | Yes | Requires explicit handling for tool results | Content filtering | Not established |
| NVIDIA NeMo Guardrails | Configurable | Partial | Execution rails | Not established |
| Meta LlamaFirewall | Yes | Supported framework integrations | Scanner-based controls | Not established |

Capabilities depend on the specific integration and configuration. "Not established" means that the reviewed documentation does not demonstrate the capability as a built-in feature.

## 4. Microsoft Prompt Shields

Microsoft Prompt Shields provides mechanisms for detecting prompt injection attempts.

It supports relevant intervention points in selected AI application integrations.

However, detecting an injection attempt is not equivalent to proving that a particular infrastructure operation is authorized.

## 5. Google Model Armor

Google Model Armor provides content assessment and security filtering capabilities for supported integrations.

These mechanisms can reduce exposure to malicious instructions.

Application-side enforcement is still relevant when using an assessment API.

## 6. AWS Bedrock Guardrails

AWS Bedrock Guardrails supports prompt attack detection and content filtering.

Its built-in prompt attack filter has limitations concerning tool-result inspection.

Applications may require additional integration logic to evaluate tool responses.

## 7. NVIDIA NeMo Guardrails

NVIDIA NeMo Guardrails allows developers to configure behavioral, retrieval, and execution controls.

It provides a flexible framework for constraining agent behavior.

Infrastructure-specific authorization still requires suitable application policies and integration.

## 8. Meta LlamaFirewall

Meta LlamaFirewall provides components for identifying security risks in AI agent workflows.

Its scanners may help detect suspicious tool responses and prompt injection patterns.

However, the proposed research additionally examines resource-level authorization and infrastructure effects.

## 9. Proposed Differentiation

The proposed Action Gateway differs in its intended enforcement point.

Rather than relying exclusively on malicious-text detection, it validates each infrastructure operation against an independently established trusted task contract.

The proposed method includes:

1. Trusted task contracts.
2. Structured tool-call validation.
3. Resource-level authorization.
4. External policy enforcement.
5. Predicted-effect validation.
6. Audit logging.

These are proposed design features, not experimentally verified advantages.

## 10. Conclusion

Existing defense solutions provide important protection mechanisms for AI applications.

Our research investigates whether infrastructure-specific authorization can improve protection against indirect prompt injection while maintaining legitimate DevOps functionality.
