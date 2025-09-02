---
title: "Homemade Plan Designer: Pragmatic Blueprinting for Power Platform"
date: 2025-08-26T19:50:00Z
author: "Jakub Bajla"
githubname: JakubBJL
categories: ["Community post"]
tags: [Power Platform, Plan Designer, Copilot, VS Code, Azure DevOps, ALM, Delivery Engineering]
type: "regular"
description: How a custom, environment-aware plan designer pipeline converts legacy artifacts + unstructured requirements into an automated, traceable Azure DevOps backlog using VS Code, Copilot, Power Platform CLI, and REST APIs.
---

## A Pragmatic Walkthrough: What Is Power Platform Plan Designer?

Plan Designer (currently evolving; some capabilities may still be in preview) is Microsoft’s copilot‑first solution blueprinting tool for Power Platform. You describe your business scenario in natural language, attach diagrams or legacy screenshots, and the tool **generates a proposed solution plan**. The best features? It interprets process flows, requirements, and (where supported) images to suggest Dataverse tables, app screens, automations, connectors, and governance considerations—tailored to your business context (subject to the platform’s present maturity, which continues to expand).

**Key capabilities:**

- **Natural Language Input:** Feed Plan Designer business scenarios, requirements, even screenshots or ERD diagrams.
- **AI-Powered Blueprinting:** It suggests a mix of Power Apps, Dataverse tables, flows, connectors, and security elements.
- **Iterative Planning:** You can refine and rerun the plan, incorporating feedback or new requirements.
- **Copilot Collaboration:** The built-in AI can answer questions, propose alternatives, and explain architectural decisions.
- **Fast Prototyping:** The output is a structured planning artifact you can translate rapidly into a working prototype.

### Where It Stops Today (and Why That Matters)

Plan Designer is brilliant for greenfield scenarios, but today it’s less opinionated about deep-diffing existing environments, enforcing custom naming standards, or wiring into bespoke ALM pipelines. If you want your blueprint to truly understand what’s already in your environment or enforce stricter governance, you extend, or build, a complementary layer.

---

## Why Build My Own? The "Homemade" Premise


Ever since Plan Designer came out, I presented it countless times, tracked reviews from fellow MVPs, watched features roll out at speed. But there was a different direction I wanted to explore, and the nudge came when I learned that Power Platform CLI now supports connecting to MCP Server. That’s when the experiment began - wiring MCP into my VS Code (Thanks, Appie! Link to blog below, in resources), where GitHub Copilot Pro was already my daily buddy.


### What is MCP Server & Why Does It Matter?

An MCP Server (preview) provides context-aware access to environment metadata—solutions, tables, relationships and selected records—subject to permissions. MCP‑aware clients (where integrations exist) can query and analyze that metadata to accelerate discovery and reuse.

Functional walkthrough:
- Stand up or connect to an MCP Server endpoint (preview feature - verify availability).
- Authenticate your client.
- Enumerate metadata (solutions, tables, relationships) and surface existing candidates for reuse.
- Drive assisted prompts: “Reuse existing table?” “Extend existing automation?” “Align to existing pattern?”

For more: official docs, community deep dives, and GitHub repos (links below).


Curiosity took over. What if I could assemble my own plan designer, one that:

- **Is Environment-Aware:** Surfaces existing tables, flows, apps, and prompts for reuse.
- **Handles Varied Documentation:** Word docs, PDFs, legacy specs—because real requirements are messy.
- **Follows My Rules:** My naming, conventions, and architectural guardrails—not only defaults.
- **Feeds Directly into Azure DevOps:** Automatically generates epics, issues, tasks with traceable tags.

---

## Step-by-Step: My Homemade Plan Designer Pipeline

### Step 1: Connect to Dev Environment & Extract Artifacts

Work against a *development* (unmanaged) environment for discovery. (Production ALM should rely on managed solutions and official deployment tooling.)

**Functional Steps:**

1. Authenticate:

       ```shell
       pac auth create --url <env-url>
       ```

2. List / export solutions (for analysis):

       ```shell
       pac solution list
       pac solution export --name <solution> --outputDirectory ./export --managed false
       ```

3. Enumerate tables:

       ```shell
       pac table list
       ```

       - Parse `customizations.xml` to catalog entities, option sets, environment variable definitions/values, workflows.
       - Assemble a configuration inventory (Name, IntendedPurpose, DeploymentScope, DefaultValue).
       - Note custom controls, web resources, process automation assets.
       - (Optional ALM hygiene) Unpack for source control:

         ```shell
         pac solution unpack --zipFile ./export/<solution>.zip --folder ./src/<solution>
         ```

### Step 2: Artifact Analysis & Domain Synthesis

Map technical artifacts into business-aligned capability domains using heuristics or lightweight classifiers:

| Artifact         | Heuristic                        | Domain               |
|------------------|----------------------------------|----------------------|
| Workflow name    | contains 'Group'                 | Identity & Access    |
| Env var name     | contains 'URL' + doc keywords    | Document Integration |
| Custom control   | reused in multiple forms/apps    | Experience / UX      |

(Extendable with regex, keyword scoring, or future embeddings.)

### Step 3: Requirements Upload & Analysis

Convert PDFs to text locally (avoid external services for sensitive content), chunk text, classify segments, and prompt an AI assistant in the editor:
> “Given these extracted lines, propose domain alignment and flag references to existing tables.”

Aggregate into candidate capability sets.

### Step 4: Backlog Engineering & Codification

Define a consistent CSV schema:

| Ref | ParentRef | Type  | Title | Description | Domain | Tags | Priority | Effort |
|-----|-----------|-------|-------|-------------|--------|------|----------|--------|
| REF-101 | (blank for Epic) | Epic | Access Management | ... | Identity & Access | IAM;REF-101 | 1 | 5 |

Use deterministic reference tags (REF-*) for traceability (the system’s numeric work item IDs are generated separately).

Create work items via Azure DevOps REST (JSON Patch, Content-Type: application/json-patch+json):

```json
[
  { "op":"add","path":"/fields/System.Title","value":"Access Management Epic" },
  { "op":"add","path":"/fields/System.Description","value":"Full HTML/Markdown description here" },
  { "op":"add","path":"/fields/System.Tags","value":"Identity & Access;REF-101" }
]
```
Check existence first (idempotency) with WIQL:
```json
{ "query": "SELECT [System.Id] FROM WorkItems WHERE [System.TeamProject] = @project AND [System.Tags] CONTAINS 'REF-101'" }
```
Conceptual “Features” collapse into Issues in the Basic process (hierarchy: Epic → Issue → Task).

### Step 5: Automated Delivery Loop

Indicative timing:

- Extraction: ~2 min
- Parsing + domain synthesis: ~2 min
- Backlog assembly: ~3 min
- Import run: <2 min

Idempotency: WIQL guard by REF tag; consistent tagging enables safe re-runs without duplication. For future drift detection, a hash or version marker could be added as an additional tag or custom field.

### Step 6: Flow Diagram (ASCII)

```text
(Env Export via CLI)
       ↓
(Artifact Parser) → (Config Catalog)
       ↓
(Domain Classifier) ← (Req Docs Ingestion)
       ↓
(Backlog Generator CSV)
       ↓
(Import Script: WIQL guard + JSON Patch)
       ↓
(Azure DevOps: Epics / Issues / Tasks tagged + refs)
       ↓
(Future Enrichment: Areas, Iterations, Telemetry Hooks)
```

---

## Technical, Architectural, and Developer Aspects

**Contract:**
- **Inputs:** Export folder (analysis only), requirements text, mapping config.
- **Outputs:** Azure DevOps epics/issues/tasks with domain + REF tags.
- **Non-Functional:** Idempotent, extensible, offline-friendly.

**Layering:** Export → Parse → Classify → Backlog → Import → (Enrich).

**Security & Governance Notes (Added):**
- Treat exports as potentially sensitive; keep in secured source control.
- Do not place secrets or personal data into AI prompts.
- Store Azure DevOps PAT in a secure secret store or environment variable - never inline.
- Managed Environments, DLP policies, and solution layering remain authoritative governance controls.

**Scope Clarification:** This pipeline accelerates *planning and analysis*, not production deployment. Official deployment should use Pipelines for Power Platform, ALM Accelerator, or equivalent.

---

## Where This Fits in ALM & Governance

This experimental pattern complements (not replaces) official tooling:
- **Use It For:** Environment discovery, capability mapping, structured backlog seeding.
- **Hand Off To:** Managed solution packaging, pipeline-based promotion, environment validation (DLP, solution checks) via standard ALM tools.
- **Governance Layers:** Managed Environments, DLP policy enforcement, solution layering strategy, policy-as-code validation (naming, publisher consistency).
- **Preview Features:** Plan Designer enhancements and MCP Server endpoints may differ across tenants; verify availability before adoption.

---

## Challenge Themes Tackled → Mechanisms

| Challenge Theme           | Mechanism / Pipeline Component                                               |
|---------------------------|-------------------------------------------------------------------------------|
| Configuration Governance  | Central variable inventory + naming validation (planned regex rules)         |
| Process Modernization     | (Planned) Workflow normalization + orchestration templates                   |
| Domain Taxonomy Sustain   | Artifact-to-domain mapping + backlog classification                          |
| Observability & Metrics   | Tagging + planned telemetry hooks for dashboards                             |
| Iterative Planning        | Future area/iteration enrichment layered on domain hierarchy                 |
| Extensibility Guardrails  | Mapping config + contract-based extensibility                                |
| Idempotent Automation     | WIQL guard + reference tag uniqueness                                       |
| Governance Reporting      | Domain tags + REF tags powering dashboards and compliance views              |

---

## Result: Reusable, Scalable Pattern

Artifacts:
- Backlog CSV template
- Parameterized import script (org/project, tag prefix)
- Classification mapping table (artifact → domain)
- Extensible flow allowing future modules (environment diff, dependency graph, policy validation)

KPIs (Track Empirically):
- Time-to-backlog (minutes)
- Requirement coverage (count of tagged references)
- Re-run consistency (no duplicate creations)

---

## Summary

In short, this experiment pulled everything together: we started by inspecting the environment and cataloging what already existed, then layered in every requirement we could gather - no matter the format. From there, we applied structure: mapped artifacts to domains, enforced naming and governance rules, and turned it all into a clean, hierarchical backlog. Finally, the entire plan flowed into Azure DevOps as traceable work items, ready for iteration and delivery. The result is a design and execution blueprint that respects what’s in place, aligns with what’s needed, and stays true to the standards we set.


---

## Final Thoughts


This homemade pipeline isn’t trying to beat the official Plan Designer - let’s be honest, Plan Designer is slick, approachable, and on a rocket of a roadmap. This is something else: a sandbox for makers, architects, and curious engineers who like taking things apart, wiring them back together, and seeing how far the platform can stretch. On a canvas as wide as Power Platform, playing around isn’t a distraction ... it’s how new patterns, reusable accelerators, and better habits get discovered.

What makes this fun is that experimentation doesn’t have to ignore the serious stuff. You can play with AI-assisted classification, custom extraction, and idempotent backlog generation while still respecting ALM discipline, Managed Environments, solution layering, DLP policies, and secure handling of exports and tokens. Governance and innovation aren’t opposing forces; when you line them up, they actually speed each other along.

The recipe here is simple: extract, learn, model, codify, automate, then iterate. Keep what works, retire what doesn’t, and feed the good pieces back into your standard toolchain (pipelines, managed solutions, dashboards). The rest of the Microsoft ecosystem - Azure DevOps, CLI tooling, AI copilots - is more than ready to meet you halfway.

So keep experimenting. Build your own accelerators. Stress-test ideas before the product ships them. The boundaries of what’s possible on the platform keep expanding, and the only real limit is how curious (and disciplined) we’re willing to be.

---

## Resources & Further Reading

- [Power Platform Plan Designer Documentation](https://learn.microsoft.com/en-us/power-apps/maker/plan-designer/plan-designer)
- [Power Platform CLI Documentation](https://learn.microsoft.com/en-us/power-platform/developer/cli/introduction)
- [Power Platform ALM Guidance](https://learn.microsoft.com/power-platform/alm/)
- [Azure DevOps Work Item REST API](https://learn.microsoft.com/en-us/rest/api/azure/devops/)
- [Azure DevOps WIQL basics](https://learn.microsoft.com/en-us/azure/devops/boards/queries/wiql-syntax)
- [JSON Patch (RFC 6902)](https://datatracker.ietf.org/doc/html/rfc6902)
- [MCP Server: Connect to Dataverse (Preview)](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/data-platform-mcp)
- [MCP Server GitHub repo (m365-galleries-mcp)](https://github.com/pnp/m365-galleries-mcp/)
- [CloudAppie: Exploring MCP Server benefits](https://www.cloudappie.nl/power-platform-cli-exploring-mcp-server-benefits/)
- [XrmBedrock on GitHub](https://github.com/delegateas/XrmBedrock)
