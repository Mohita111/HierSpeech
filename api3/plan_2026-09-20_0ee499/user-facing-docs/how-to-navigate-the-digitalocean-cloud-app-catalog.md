# How to Navigate the DigitalOcean Cloud App Catalog

The DigitalOcean Cloud App Catalog brings together deployment and integration guides for tools you can run on DigitalOcean infrastructure. Each guide is tied to a DigitalOcean Marketplace 1-Click App and explains what the software includes, how to launch it, and how to begin using it after launch.

This guide helps you understand the catalog structure, choose the right guide for your infrastructure need, read the guides consistently, and find the official Marketplace page behind each one.

---

## Find the Right Guide for Your Need

Use this quick reference to jump to the correct guide.

| If you need... | Use this guide | Catalog category |
|---|---|---|
| A private, self-hosted password manager for individuals or teams | Bitwarden | Security & Identity |
| Shared object-storage access for applications running on Kubernetes | CSI for S3 | Storage & Volume Plugins |
| Visibility into generative AI performance, usage, and costs | OpenLIT | Observability & LLM Monitoring |
| Secure, identity-based remote access to private resources | Pangolin (CE) | Managed Databases |

> **Note:** Pangolin (CE) appears in the Managed Databases section of this catalog, but its deployment guide focuses on a secure remote access platform. Keep this distinction in mind when using the category list.

---

## Catalog Categories at a Glance

### Security & Identity

**Bitwarden** is an open-source password management tool for individuals, teams, and business organizations. The guide shows you how to create a Droplet with Bitwarden pre-installed and complete the first-login setup.

Use this guide when you want:
- A self-hosted password vault
- Control over where credentials are stored
- Automatic updates for the Bitwarden server

### Storage & Volume Plugins

**CSI for S3** connects a DigitalOcean Spaces Object Storage bucket to a Kubernetes cluster as shared storage. This lets multiple pods read from and write to the same bucket as if it were a file system.

Use this guide when you need:
- Shared storage across multiple Kubernetes workloads
- Object storage mounted inside a cluster
- Guidance on creating storage classes, persistent volumes, and example workloads

### Observability & LLM Monitoring

**OpenLIT** is an open-source observability and monitoring platform for AI agents and large language models. It tracks prompts, token usage, latency, cost, and performance.

Use this guide when you need:
- Real-time visibility into AI and LLM workloads
- Error and exception tracking
- Prompt management and cost analytics
- Built-in dashboards for model and application performance

### Managed Databases

**Pangolin (CE)** provides an identity-based remote access platform built on WireGuard. It combines reverse proxy and VPN capabilities to give browser-based access to web applications and client-based access to private resources.

Use this guide when you need:
- Secure access to private or public resources
- Granular access control and zero-trust security
- A self-hosted remote access layer

---

## What Each Guide Covers

### Bitwarden

The Bitwarden guide covers:

- What software is included and under which license
- How to create a Bitwarden Droplet from the DigitalOcean control panel
- How to create the same Droplet using the DigitalOcean API
- What you need before you start, including a hostname and an installation ID and key from Bitwarden
- How Bitwarden requires at least 2 GB of memory
- How automatic updates and server settings work after deployment

### CSI for S3

The CSI for S3 guide covers:

- How the CSI driver turns a Spaces bucket into Kubernetes storage
- How to install the 1-Click application using the control panel or API
- How to verify the new storage class is available
- How to connect the storage class to a Spaces bucket
- How to create a persistent volume claim and an example workload
- Performance benchmark results for common file operations
- How to upgrade and uninstall the CSI driver

### OpenLIT

The OpenLIT guide covers:

- OpenLIT features, including AI agent observability, prompt management, and cost tracking
- How to install the 1-Click application on a Kubernetes cluster
- How to verify that OpenLIT is running
- How to access the OpenLIT dashboard
- Default login steps
- How to send AI and LLM telemetry to OpenLIT
- Next-step resources for dashboards, prompt experiments, GPU monitoring, and more

### Pangolin (CE)

The Pangolin guide covers:

- How to create a Droplet with Pangolin pre-installed
- DNS configuration steps for pointing a domain at your new Droplet
- First-login setup through an automated script
- How to access the Pangolin dashboard
- Security considerations, including firewall and two-factor authentication setup
- How to apply future updates
- Troubleshooting steps for access and connectivity issues

---

## Marketplace Catalog Pages and Metadata

Every guide maps to a DigitalOcean Marketplace catalog page. The guide metadata records the Marketplace product type, the official documentation URL, and a last-updated date.

| Guide | Marketplace product type | Marketplace catalog page | Last updated |
|---|---|---|---|
| Bitwarden | Marketplace 1-Click App | [Bitwarden Marketplace page](https://marketplace.digitalocean.com/apps/bitwarden) | 2026-06-11 |
| CSI for S3 | Marketplace Kubernetes 1-Click App | [CSI for S3 Marketplace page](https://marketplace.digitalocean.com/apps/csi-for-s3) | 2024-06-17 |
| OpenLIT | Marketplace Kubernetes 1-Click App | [OpenLIT Marketplace page](https://marketplace.digitalocean.com/apps/openlit) | 2025-11-13 |
| Pangolin (CE) | Marketplace 1-Click App | [Pangolin (CE) Marketplace page](https://marketplace.digitalocean.com/apps/pangolin-ce-1) | 2026-03-18 |

Each guide also includes an official DigitalOcean documentation URL. For example, the Bitwarden guide maps to the Bitwarden catalog page in the DigitalOcean documentation, while the CSI for S3 guide maps to its own catalog page.

---

## Reading Conventions Across Guides

The guides follow a consistent structure so you can find the information you need quickly.

### Software Included Table

Every guide includes a **Software Included** table that shows:

- The main package name
- The version included in the deployment
- The license under which the software is distributed

This helps you understand what you are installing and whether the included version meets your requirements.

### Control Panel and API Deployment Paths

Every guide provides two deployment paths:

1. **Control panel deployment:** A one-click button that creates the resource directly in your DigitalOcean account.
2. **API deployment:** Instructions for creating the same resource programmatically using the DigitalOcean API or command-line tooling.

The control panel path is generally the fastest way to start. Use the API path when you need automation, repeatable deployment, or infrastructure-as-code workflows.

### Step-by-Step Deployment Blueprint

After deployment, each guide follows a **Getting Started** section that walks through the first meaningful actions. The exact steps vary by guide but typically include:

- Verifying the deployment
- Connecting or accessing the application
- Configuring initial settings
- Testing the deployment

### Guide-Specific Extras

Some guides include additional material that is useful for advanced decisions:

- **CSI for S3** includes performance benchmarks and upgrade/uninstall steps.
- **OpenLIT** includes feature descriptions, telemetry quickstart links, and next-step resources.
- **Pangolin (CE)** includes DNS setup, security recommendations, and troubleshooting.

---

## Requesting or Contributing a New Catalog Entry

The catalog source reviewed for this navigation guide does not include a published step-by-step process for requesting or contributing a new entry. If you need a deployment guide that is not currently present, the recommended next step is to contact DigitalOcean Marketplace support or consult the official DigitalOcean Marketplace vendor information.

When evaluating a potential new entry, the catalog currently groups guides into four main areas:

- Security & Identity
- Storage & Volume Plugins
- Observability & LLM Monitoring
- Managed Databases

A new guide would typically follow the same structure as the existing entries: a clear summary, software-included table, deployment steps through the control panel and API, and a getting-started walkthrough.