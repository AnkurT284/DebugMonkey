# DebugMonkey

**An AI-powered debugging agent harness for automated root cause analysis across distributed backend systems.**

**Project Status:** Planning and Initial Development

## Overview

DebugMonkey is an open-source personal engineering project focused on designing and building an AI-powered debugging agent harness capable of investigating failures across multiple backend services.

The project aims to explore how Large Language Models (LLMs), agent orchestration, tool integration, and automated validation can be combined to assist developers in identifying root causes of complex software failures.

Rather than relying on unrestricted autonomous agents, DebugMonkey will follow a structured, evidence-driven investigation process with explicit execution boundaries, traceable decisions, and measurable outcomes.

The project is being developed incrementally, with an emphasis on understanding the underlying engineering principles, evaluating architectural trade-offs, and building reliable agentic systems.

## Motivation

Debugging failures in distributed systems often requires engineers to manually correlate information from multiple sources, including:

- Application logs and distributed traces
- Source code across interconnected services
- Git commit history and code changes
- Exception stack traces
- Service dependencies and execution flows
- Existing test cases and deployment information

Although LLMs can assist in interpreting this information, building a dependable debugging agent requires more than integrating a model with external tools.

A reliable system must manage investigation context, orchestrate tool execution, validate hypotheses, handle failures, and distinguish evidence-supported conclusions from assumptions.

DebugMonkey is an effort to study and implement these capabilities through practical engineering.

## Objectives

The primary objectives of DebugMonkey are:

1. **Automated Investigation:** Develop agents capable of investigating debugging issues using source code, logs, traces, and Git history.

2. **Cross-Service Root Cause Analysis:** Reconstruct execution paths across backend services and identify potential failure origins.

3. **Evidence-Based Reasoning:** Ensure investigation conclusions are supported by verifiable technical evidence.

4. **Structured Agent Orchestration:** Implement controlled investigation workflows with state management, conditional execution, and termination criteria.

5. **Tool Interoperability:** Explore the Model Context Protocol (MCP) for integrating debugging tools and external data sources.

6. **Automated Validation:** Evaluate potential root causes and proposed changes through reproducible tests.

7. **Agent Reliability and Evaluation:** Establish benchmarks for measuring investigation accuracy, evidence quality, execution efficiency, and failure handling.

## Proposed Architecture

DebugMonkey will follow a modular architecture separating agent orchestration, investigation tools, external integrations, and validation.

```text
                  Debugging Request
                         |
                         v
                Investigation Intake
                         |
                         v
                Investigation Planner
                         |
                         v
                Agent Orchestration
                    (LangGraph)
                         |
            +------------+------------+
            |            |            |
            v            v            v
       Code Analysis  Log Analysis  Git Analysis
            |            |            |
            +------------+------------+
                         |
                         v
                Evidence Aggregation
                         |
                         v
               Hypothesis Evaluation
                         |
                +--------+--------+
                |                 |
                v                 v
        Additional Investigation  RCA Report
                                          |
                                          v
                                Optional Validation
                                          |
                                          v
                               Final Investigation
                                     Report
```

The architecture will evolve as the project progresses. Initial implementations will prioritize simple, deterministic tools before introducing more advanced orchestration and integrations.

## Planned Technology Stack

| Component | Technology |
|---|---|
| Primary Development Language | Python |
| Agent Orchestration | LangGraph |
| LLM Integration | Provider-agnostic LLM APIs |
| Tool Integration | Model Context Protocol (MCP) |
| Data Validation | Pydantic |
| Backend Test Environment | Java, Spring Boot |
| Source Code Analysis | Git, ripgrep |
| Log Analysis | Structured logs, ELK-compatible data |
| Automated Testing | pytest, JUnit |
| Execution Isolation | Docker |
| Agent Evaluation | Custom evaluation framework |

Technologies may be added, removed, or replaced based on implementation requirements and evaluation results.

## Development Roadmap

Development is organized around independently verifiable engineering milestones rather than fixed release dates.

| Milestone | Description | Status |
|---|---|---|
| M0 | Project requirements, scope definition, and architecture planning | In Progress |
| M1 | Deterministic debugging tools for source code, Git, and log inspection | Planned |
| M2 | Reproducible multi-service debugging environment | Planned |
| M3 | Initial LLM-powered investigation agent with tool calling | Planned |
| M4 | Stateful agent orchestration using LangGraph | Planned |
| M5 | MCP integration and cross-service root cause analysis | Planned |
| M6 | Evaluation framework and reliability benchmarking | Planned |
| M7 | Sandboxed fix generation and automated test verification | Planned |

Each milestone will include documented requirements, implementation decisions, automated tests, and demonstrable outcomes.

## Engineering Principles

The project follows several core development principles.

### 1. Evidence-Driven Investigation

Agent conclusions must be grounded in retrieved source code, logs, traces, or executable test results. Unsupported hypotheses should be explicitly identified.

### 2. Deterministic Tool Execution

External tools should expose well-defined interfaces, validate inputs, enforce execution boundaries, and return structured results.

### 3. Controlled Agent Autonomy

Agent execution must operate within defined limits, including tool permissions, iteration budgets, error handling, and termination conditions.

### 4. Incremental Complexity

Advanced architectures will be introduced only when justified by measurable requirements. The initial implementation will favor simplicity, observability, and maintainability.

### 5. Evaluation-Driven Development

Agent behavior will be evaluated against reproducible debugging scenarios to identify reasoning failures, inaccurate conclusions, and inefficient investigation strategies.

### 6. Human Oversight

Operations involving source code modifications, execution of generated changes, or access to sensitive environments will require appropriate safeguards and human authorization.

## Evaluation Strategy

DebugMonkey will use a collection of known debugging scenarios to measure investigation performance.

Planned evaluation dimensions include:

| Metric | Description |
|---|---|
| Root Cause Accuracy | Correctness of the identified failure origin |
| Evidence Validity | Accuracy and relevance of referenced technical evidence |
| Investigation Completeness | Coverage of relevant execution paths and potential causes |
| Tool Efficiency | Number and relevance of tool invocations |
| Execution Cost | Model usage and computational cost per investigation |
| Failure Handling | Ability to recover from tool errors and incomplete information |
| Validation Success | Ability to reproduce and verify identified failures |

Evaluation results and benchmark methodology will be documented as the project matures.

## Development Approach

DebugMonkey is developed using a milestone-based software engineering process.

AI-assisted development tools, including Claude Code and Codex, may be used for implementation support, design evaluation, code review, and testing.

Architectural decisions, technical requirements, validation criteria, and final implementation reviews remain developer-driven.

The objective is to develop a thorough understanding of agent architecture and harness engineering rather than relying on generated implementations without verification.

## Development Updates

This project is also part of a public technical learning initiative focused on AI engineering and agentic systems.

Progress will be documented through:

- **GitHub:** Source code, architectural decisions, milestones, and technical documentation.
- **LinkedIn:** Weekly engineering updates, implementation insights, and lessons learned.
- **X (Twitter):** Development progress, experiments, and concise technical observations.

Updates will focus on implementation details, engineering challenges, architectural trade-offs, and evaluation outcomes.

Technical development logs will be maintained under `docs/build-log/` as the project progresses.

## Current Status

DebugMonkey is currently in its initial planning phase.

The architecture, technology choices, and planned capabilities described in this repository represent development objectives and are subject to change.

Implementation instructions, supported integrations, and executable examples will be added as their respective milestones are completed.

## Inspiration

This project is inspired by engineering approaches to AI-assisted debugging, including Uber's publicly discussed debugging agent harness.

DebugMonkey is an independent personal project and is not affiliated with, endorsed by, or maintained by Uber.

## License

A license has not yet been selected. Until a license is added, no open-source usage or redistribution rights are granted by this repository.

---

**DebugMonkey — An engineering exploration of reliable, evidence-driven AI debugging agents.**
