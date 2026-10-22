# Project Status — First Probationary Period

## 1. Project Information

**Project Title:** Development and Experimental Evaluation of a Method for Protecting DevOps Agents Against Indirect Prompt Injection During Infrastructure Operations

**University:** Astana IT University

**Degree Program:** Software Engineering

**Team Members:**
- Sanzhar Sagatov
- Aiat Mergenbay

**Research Supervisor:** Kamila Tanyrbergenova

**Current Stage:** Research and System Design

**Submission Version:** prob-period-1

## 2. Current Project Status

The project has reached the initial research and system design stage.

The team has prepared the theoretical foundation, preliminary system architecture, requirements specification, and experimental evaluation methodology.

The following project materials are available:

### 2.1 Research and Problem Analysis

- Defined the research problem related to indirect prompt injection attacks against DevOps agents.
- Formulated the research objective and three research questions.
- Identified potential attack surfaces, including CI/CD logs, README files, pull requests, infrastructure configurations, and tool responses.
- Defined the preliminary threat model and security boundaries.

### 2.2 Literature Review

- Prepared a review covering 14 scientific publications.
- Examined existing approaches to indirect prompt injection detection and prevention.
- Identified limitations of existing approaches in infrastructure automation environments.
- Formulated the research gap addressed by the proposed method.

### 2.3 Comparative Analysis

Prepared a comparative analysis of five existing security solutions:

1. Microsoft Prompt Shields
2. Google Model Armor
3. AWS Bedrock Guardrails
4. NVIDIA NeMo Guardrails
5. Meta LlamaFirewall

The comparison considers injection detection, tool-response inspection, authorization mechanisms, configuration capabilities, and infrastructure-specific protection.

### 2.4 Requirements Specification

Prepared the initial functional and nonfunctional requirements.

The requirements cover:

- Trusted task contracts
- Data provenance tracking
- Infrastructure tool-call normalization
- Authorization policy enforcement
- Predicted-effect verification
- Audit logging
- Security isolation
- Experimental reproducibility

### 2.5 System Architecture

Designed the proposed architecture of a contract-bound Action Gateway.

Prepared the following diagrams:

1. System Context Diagram
2. Use Case Diagram
3. Component Architecture Diagram

The architecture defines how proposed infrastructure operations will be validated before execution.

### 2.6 Experimental Evaluation Design

Prepared the initial experimental methodology, including:

- Attack scenarios and injection surfaces
- Attacker objectives and assumptions
- Baseline defense configurations
- Evaluation metrics
- Experimental procedures
- Reproducibility requirements

The primary evaluation metrics include unauthorized-action attack success rate, legitimate-task success rate, false denial rate, and execution latency.

## 3. Team Responsibilities

### 3.1 Sanzhar Sagatov

**Area of Responsibility:** Security Architecture, System Requirements, and Backend Development

Primary responsibilities:

- Research problem and threat model definition
- Security architecture design
- Trusted task contract specification
- Action Gateway design and implementation
- Authorization policy integration
- Infrastructure operation validation
- API design
- Technical documentation
- Integration of the security components

**Related Documentation:**
- docs/proposal.md
- docs/architecture.md
- docs/requirements.md
- docs/diagrams/

**Planned Development Responsibilities:**
- Implement the Action Gateway prototype.
- Develop structured infrastructure operation validation.
- Integrate authorization policies.
- Implement audit logging.
- Develop tests for authorized and unauthorized operations.

### 3.2 Aiat Mergenbay

**Area of Responsibility:** Security Research, Experimental Design, and Testing

Primary responsibilities:

- Literature review and related-work analysis
- Comparison of existing prompt injection defense systems
- Experimental evaluation methodology
- Attack scenario design
- Testing strategy
- Baseline defense comparisons
- Research documentation
- Experimental results analysis

**Related Documentation:**
- docs/literature-review.md
- docs/existing-solutions.md
- docs/evaluation-plan.md
- research/references.md

**Planned Development Responsibilities:**
- Develop reproducible prompt injection test scenarios.
- Prepare an isolated experimental environment.
- Implement automated experimental tests.
- Conduct baseline comparisons.
- Analyze security and performance metrics.
- Prepare experimental results and conclusions.

**Note:** Individual completed contributions are tracked through the corresponding YouTrack tasks and GitHub history. Assigned responsibilities do not by themselves indicate completed work.

## 4. Current Limitations

The project currently has the following limitations:

1. The Action Gateway has not yet been validated as a working software prototype.
2. The infrastructure testing environment has not yet been experimentally verified.
3. Quantitative experimental results are not yet available.
4. The effectiveness of the proposed protection mechanism has not been empirically established.
5. The planned system requires further implementation and integration testing.
6. User interviews and formal supervisor feedback remain pending.

These limitations are consistent with the project's current research and design stage.

## 5. Next Development Stage

The next stage will focus on implementing and experimentally evaluating the proposed protection mechanism.

### 5.1 Prototype Development

- Implement the first version of the Action Gateway.
- Develop the trusted task contract mechanism.
- Integrate an external authorization policy engine.
- Implement structured validation of infrastructure operations.
- Add security audit logging.

### 5.2 Experimental Environment

- Prepare an isolated Kubernetes testing environment.
- Configure synthetic infrastructure resources.
- Develop reproducible experimental scenarios.
- Implement environment reset and state verification.

### 5.3 Security Testing

- Test authorized infrastructure operations.
- Test unauthorized operations triggered by injected instructions.
- Evaluate the effectiveness of security policies.
- Verify that denied operations do not reach the infrastructure executor.

### 5.4 Experimental Evaluation

- Compare the proposed method with baseline defenses.
- Measure unauthorized-action attack success rates.
- Evaluate legitimate-task completion.
- Measure false denials and performance overhead.
- Analyze residual vulnerabilities.

### 5.5 Research Documentation

- Document implementation decisions.
- Collect experimental results.
- Update the system architecture.
- Record supervisor feedback.
- Prepare the next diploma submission materials.

## 6. Project Management

The project uses the following collaboration tools:

**GitHub:** Version control, source code, architecture documentation, and contribution history.

**YouTrack:** Task assignment, progress tracking, and individual contribution management.

**Git:** Version control and submission version management.

The first probationary-period submission will be identified by the Git tag `prob-period-1`.

Each subsequent development stage will include updated documentation, implementation progress, testing results, and individual contributions.

## 7. Conclusion

The current project stage establishes the research foundation, requirements, proposed architecture, and experimental methodology for protecting DevOps agents against indirect prompt injection.

The next stage will focus on implementing the proposed Action Gateway and conducting reproducible experiments to evaluate its security effectiveness and operational overhead.