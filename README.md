# TSCLab: IBM Agentic Engineering Suite Hackathon

Welcome to the **TSCLab** repository. This repository contains the lab guide and baseline codebase for the **IBM Agentic Engineering Suite Hackathon** (Nashville, April 2026). The lab is designed to demonstrate the power of IBM's Agentic Engineering tools, including IBM DOORS Next, IBM Engineering Assistant, and IBM Project Bob, in modernizing and accelerating software development workflows.

## Repository Contents

This repository provides a complete codebase package and directions, bundled together to contain everything necessary for developers to complete the lab.

- **`IBM Agentic Engineering Lab Guide.pdf`** (and `.docx`): The comprehensive step-by-step guide for the hackathon. It covers accessing the lab environment, using the AI Engineering Assistant to generate requirements, and completing the various hackathon tracks.
- **`ucth-baseline-with-webmethods.zip`**: The baseline codebase for the Unified Carrier Tracking Hub (UCT Hub) lab. This archive contains the intentionally buggy starting state for Lab 3, along with the Solutions Designer architecture artifacts from Lab 2.

## Hackathon Overview

The hackathon focuses on using AI agents to automate and accelerate various stages of the software development lifecycle (SDLC). Participants will use the IBM Agentic Requirements tool to derive, enter, and quality-analyze software requirements from Jira-style tickets.

### Lab 1: Agentic Requirements Generation

In this lab, participants will access the IBM DOORS Next environment and use the Engineering Assistant to generate requirements for one of five specific tracks.

#### Available Tracks

1. **Java Modernization Advisor**: Build an automated advisor that scans legacy Java classes (using deprecated `javax` APIs and Spring patterns), identifies modernization opportunities, and generates a prioritized refactoring plan to migrate to Java 21.
2. **Incident Copilot**: Create an autonomous copilot that correlates alerts from PagerDuty, logs from Splunk, and metrics from Datadog to identify root causes and generate remediation runbooks, reducing mean time to resolution.
3. **Legacy IMS MCP Wrapper**: Wrap a legacy inventory management system (IMS) with Model Context Protocol (MCP) tools, providing proper input/output schemas and safety guardrails so AI agents can safely query and update inventory.
4. **DevOps Artifact Generator**: Develop an automated generator that accepts a service descriptor and instantly produces correctly formatted Markdown ADRs, Ansible playbooks, and Tekton Pipeline manifests.
5. **Agentic Workflow Orchestrator**: Build an orchestrator that accepts a natural-language prompt, decomposes it into an ordered execution plan, and runs each step against the appropriate tool to trigger a complete deployment workflow.

## Baseline Codebase (UCT Hub)

The `ucth-baseline-with-webmethods.zip` file contains the starting state for the Unified Carrier Tracking Hub. It includes a microservices architecture built with Quarkus, featuring services for Order Management (`tsc-oms`), Store Operations (`tsc-store-ops`), Notifications (`tsc-notifications`), and more.

### Key Features of the Baseline

- **Intentionally Buggy State**: The codebase contains specific bugs in the `tsc-oms`, `tsc-store-ops`, and `tsc-notifications` services. Participants will use IBM Project Bob to find and fix these issues during Lab 3.
- **Architecture Artifacts**: The `src-design/` directory includes IBM DevOps Solution Workbench artifacts, such as C4 models, domain diagrams, and Architectural Decision Records (ADRs).
- **Carrier Tracking MCP Server**: A pre-built MCP server (`src-mcp/carrier-tracking-mcp-server/`) that connects IBM Project Bob directly to the IBM webMethods API Gateway for live carrier tracking data.

## Getting Started

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Sheldonos/TSCLab.git
   cd TSCLab
   ```

2. **Review the Lab Guide**:
   Open `IBM Agentic Engineering Lab Guide.pdf` and follow the instructions to access the lab environment and begin Lab 1.

3. **Extract the Baseline Codebase**:
   Unzip the `ucth-baseline-with-webmethods.zip` file to access the UCT Hub microservices and architecture artifacts.
   ```bash
   unzip ucth-baseline-with-webmethods.zip -d ucth-baseline
   ```

4. **Connect to IBM Project Bob**:
   Open the extracted `ucth-baseline` folder in IBM Project Bob. Bob will automatically index the codebase using the provided `k5-project.yml` manifest.

## Running the Services Locally

Each service in the baseline codebase is a Quarkus application. To run any service in development mode:

```bash
cd ucth-baseline/tsc-oms
./mvnw quarkus:dev
```

Swagger UI will be available at `http://localhost:{port}/swagger-ui` for each running service.

---
*This repository is maintained for the IBM Agentic Engineering Suite Hackathon.*
