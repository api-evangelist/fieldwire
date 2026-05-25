# Fieldwire (fieldwire)
Fieldwire is real-time construction jobsite management software acquired by Hilti Group in 2021. The platform helps general contractors, specialty contractors, project owners, architects, and designers coordinate plans, tasks, forms, RFIs, submittals, and project financials across more than 4 million jobsites worldwide. The Fieldwire REST API (v3.1) exposes the full data plane — Account, Projects, Tasks, Plans/Sheets, Forms, Attachments (S3-direct), Project Financials, RFIs, Submittals, and Webhooks — across US and EU regional hosts, with documentation auto-generated and hosted at developers.fieldwire.com.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/fieldwire/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

 - Construction, Construction Technology, ConTech, Field Management, Punch List, Plans, Drawings, BIM, Forms, Inspections, Project Management, Hilti

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Plans

| Plan | Per User / Month | Key Features |
|---|---|---|
| Basic | $0 (max 5 users, 3 projects, 100 sheets) | Plan viewing, task management, files, photos |
| Pro | $39 | Unlimited projects + sheets, reports, sheet compare, custom statuses |
| Business | $64 | Custom forms, integrations, BIM viewer, Field Intelligence AI |
| Business Plus | $89 | RFIs, submittals, change orders, budget management |
| Custom Contracts | Call sales | API access, SSO, unlimited users, dedicated success |

API access is unlocked in the Custom Contracts tier.

## APIs

### Fieldwire Account API
Account-scoped (super) endpoints used to authenticate, exchange the long-lived API key for a short-lived JWT access token, and manage account-level users, roles, attachments, data types, custom stamps, form templates, and project transfers. Calls hit `https://client-api.super.fieldwire.com`.

**Human URL:** [https://developers.fieldwire.com/docs/getting-started](https://developers.fieldwire.com/docs/getting-started)

- [Documentation — Getting Started](https://developers.fieldwire.com/docs/getting-started)
- [Documentation — Authentication](https://developers.fieldwire.com/docs/authentication)
- [OpenAPI](openapi/fieldwire-account-api-openapi.yml)
- [Naftiko Capability — Authentication](capabilities/account-authentication.yaml)
- [Naftiko Capability — Users](capabilities/account-users.yaml)

### Fieldwire Projects API
Project lifecycle, archival, transfer, synchronisation, users, teams, and statistics. Project data is region-resident — US accounts use `client-api.us.fieldwire.com/api/v3`, EU accounts use `client-api.eu.fieldwire.com/api/v3`.

**Human URL:** [https://developers.fieldwire.com/reference/get_projects_in_account](https://developers.fieldwire.com/reference/get_projects_in_account)

- [OpenAPI](openapi/fieldwire-projects-api-openapi.yml)
- [Naftiko Capability — Projects](capabilities/projects-projects.yaml)

### Fieldwire Tasks API
Create and manage construction tasks — punch list items, inspections, work assignments — including check items (up to 500 per task), task relations, custom attributes, and bubbles (comments, photos, video, attachments).

**Human URL:** [https://developers.fieldwire.com/reference/get_tasks_in_project](https://developers.fieldwire.com/reference/get_tasks_in_project)

- [Documentation — Custom Task Attributes](https://developers.fieldwire.com/docs/custom-task-attributes)
- [OpenAPI](openapi/fieldwire-tasks-api-openapi.yml)
- [JSON Schema — Task](json-schema/fieldwire-task-schema.json)
- [Naftiko Capability — Tasks](capabilities/tasks-tasks.yaml)
- [Naftiko Capability — Bubbles](capabilities/tasks-bubbles.yaml)

### Fieldwire Plans and Sheets API
Upload PDF drawing sets, manage sheet versioning, organise floorplans into hierarchical collections, link sheets to one another, and attach versioned Building Information Models.

**Human URL:** [https://developers.fieldwire.com/docs/uploading-plans-via-api](https://developers.fieldwire.com/docs/uploading-plans-via-api)

- [Documentation — Floorplan Collections](https://developers.fieldwire.com/docs/floorplan-collections-api-guide)
- [OpenAPI](openapi/fieldwire-plans-api-openapi.yml)
- [Naftiko Capability — Floorplans](capabilities/plans-floorplans.yaml)
- [Naftiko Capability — Sheets](capabilities/plans-sheets.yaml)

### Fieldwire Forms API
Author account-level form templates and capture project-level form records — daily reports, safety inspections, QA/QC checklists, signatures, markups, and custom data collection.

**Human URL:** [https://developers.fieldwire.com/docs/working-with-project-forms](https://developers.fieldwire.com/docs/working-with-project-forms)

- [Documentation — Getting Form Data](https://developers.fieldwire.com/docs/getting-form-data)
- [OpenAPI](openapi/fieldwire-forms-api-openapi.yml)
- [Naftiko Capability — Form Templates](capabilities/forms-form-templates.yaml)
- [Naftiko Capability — Form Records](capabilities/forms-form-records.yaml)

### Fieldwire Attachments and Media API
Two-step direct-to-S3 upload flow: request a 1-day signed AWS POST token, push the binary directly to S3, then register the attachment in Fieldwire. GeoJSON markup overlays (arrow, drawing, measurement, text) can be flattened into thumbnails.

**Human URL:** [https://developers.fieldwire.com/reference/add_aws_post_tokens](https://developers.fieldwire.com/reference/add_aws_post_tokens)

- [OpenAPI](openapi/fieldwire-attachments-api-openapi.yml)
- [Naftiko Capability — Attachments](capabilities/attachments-attachments.yaml)
- [Naftiko Capability — Markups](capabilities/attachments-markups.yaml)

### Fieldwire Project Financials API
Budget line items, actual costs, tier cost codes, and change orders for Business Plus customers.

**Human URL:** [https://developers.fieldwire.com/reference/get_budget_line_items_in_project](https://developers.fieldwire.com/reference/get_budget_line_items_in_project)

- [OpenAPI](openapi/fieldwire-financials-api-openapi.yml)
- [Naftiko Capability — Budget](capabilities/financials-budget.yaml)
- [Naftiko Capability — Change Orders](capabilities/financials-change-orders.yaml)

### Fieldwire RFIs and Submittals API
Requests for Information, submittals, submittal types, spec sections, watchers, approvals, and submittal log extraction. Supports email-based responses and ball-in-court reassignments.

**Human URL:** [https://developers.fieldwire.com/reference/get_rfis_in_project](https://developers.fieldwire.com/reference/get_rfis_in_project)

- [OpenAPI](openapi/fieldwire-rfis-submittals-api-openapi.yml)
- [Naftiko Capability — RFIs](capabilities/rfis-rfis.yaml)
- [Naftiko Capability — Submittals](capabilities/submittals-submittals.yaml)

### Fieldwire Webhooks API
Subscribe to real-time event notifications for 14 entity types (attachments, entity tags / taggings, floorplans, forms, hyperlinks, multi-hyperlinks, projects, project resource links, sheets, sheet uploads, tasks, task check items, task relations). Per-subscription `entity_filters` (max 20) and `project_filters` (max 100) narrow delivery.

**Human URL:** [https://developers.fieldwire.com/docs/beta-creating-webhook-configurations](https://developers.fieldwire.com/docs/beta-creating-webhook-configurations)

- [Documentation — Event Types](https://developers.fieldwire.com/docs/webhook-event-types)
- [Documentation — Event Filters](https://developers.fieldwire.com/docs/webhook-filters)
- [OpenAPI](openapi/fieldwire-webhooks-api-openapi.yml)
- [AsyncAPI](asyncapi/fieldwire-webhooks-asyncapi.yml)
- [Naftiko Capability — Subscriptions](capabilities/webhooks-subscriptions.yaml)

## Common Properties

- [Portal — fieldwire.com](https://www.fieldwire.com)
- [Developer Portal — developers.fieldwire.com](https://developers.fieldwire.com)
- [GettingStarted](https://developers.fieldwire.com/docs/getting-started)
- [Authentication](https://developers.fieldwire.com/docs/authentication)
- [RateLimits](https://developers.fieldwire.com/docs/rate-limiting)
- [Documentation — Pagination](https://developers.fieldwire.com/docs/pagination)
- [Documentation — Filtering](https://developers.fieldwire.com/docs/filtering)
- [Versioning](https://developers.fieldwire.com/docs/versioning)
- [FAQ](https://developers.fieldwire.com/docs/frequently-asked-questions)
- [ChangeLog — API](https://developers.fieldwire.com/changelog)
- [RSS — API Changelog](https://developers.fieldwire.com/changelog.rss)
- [ChangeLog — Product](https://www.fieldwire.com/changelog/)
- [StatusPage — status.fieldwire.com](https://status.fieldwire.com/)
- [Support — Help Center](https://help.fieldwire.com/hc/en-us)
- [Documentation — Help Center API Intro](https://help.fieldwire.com/hc/en-us/articles/205097173-Introduction-to-the-Fieldwire-API)
- [Documentation — Integrations](https://www.fieldwire.com/integrations/)
- [Documentation — API Integration Page](https://www.fieldwire.com/integrations/fieldwire/api/)
- [GitHubOrganization](https://github.com/Fieldwire)
- [SDK — Ruby Sample Client](https://github.com/Fieldwire/fieldwire_ruby_sample)
- [SDK — Java Sample Client](https://github.com/Fieldwire/fieldwire_java_sample)
- [Pricing](https://www.fieldwire.com/pricing/)
- [Security](https://www.fieldwire.com/security/)
- [PrivacyPolicy](https://www.fieldwire.com/privacy/)
- [TermsOfService](https://www.fieldwire.com/terms/)
- [LinkedIn](https://www.linkedin.com/company/fieldwire)
- [Twitter / X](https://twitter.com/Fieldwire)
- [YouTube](https://www.youtube.com/@fieldwire)
- [Parent Company — Hilti](https://www.hilti.com)

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [Fieldwire Account API](openapi/fieldwire-account-api-openapi.yml)
- [Fieldwire Projects API](openapi/fieldwire-projects-api-openapi.yml)
- [Fieldwire Tasks API](openapi/fieldwire-tasks-api-openapi.yml)
- [Fieldwire Plans and Sheets API](openapi/fieldwire-plans-api-openapi.yml)
- [Fieldwire Forms API](openapi/fieldwire-forms-api-openapi.yml)
- [Fieldwire Attachments and Media API](openapi/fieldwire-attachments-api-openapi.yml)
- [Fieldwire Project Financials API](openapi/fieldwire-financials-api-openapi.yml)
- [Fieldwire RFIs and Submittals API](openapi/fieldwire-rfis-submittals-api-openapi.yml)
- [Fieldwire Webhooks API](openapi/fieldwire-webhooks-api-openapi.yml)

### AsyncAPI

- [Fieldwire Webhooks](asyncapi/fieldwire-webhooks-asyncapi.yml)

### JSON Schema

- [Fieldwire Task](json-schema/fieldwire-task-schema.json)

### JSON-LD

- [Fieldwire Context](json-ld/fieldwire-context.jsonld)

### Capabilities (Naftiko)

- [Account — Authentication](capabilities/account-authentication.yaml)
- [Account — Users](capabilities/account-users.yaml)
- [Projects](capabilities/projects-projects.yaml)
- [Tasks](capabilities/tasks-tasks.yaml)
- [Tasks — Bubbles](capabilities/tasks-bubbles.yaml)
- [Plans — Floorplans](capabilities/plans-floorplans.yaml)
- [Plans — Sheets](capabilities/plans-sheets.yaml)
- [Forms — Form Templates](capabilities/forms-form-templates.yaml)
- [Forms — Form Records](capabilities/forms-form-records.yaml)
- [Attachments](capabilities/attachments-attachments.yaml)
- [Attachments — Markups](capabilities/attachments-markups.yaml)
- [Financials — Budget](capabilities/financials-budget.yaml)
- [Financials — Change Orders](capabilities/financials-change-orders.yaml)
- [RFIs](capabilities/rfis-rfis.yaml)
- [Submittals](capabilities/submittals-submittals.yaml)
- [Webhooks — Subscriptions](capabilities/webhooks-subscriptions.yaml)

### Spectral Rules

- [Fieldwire Spectral Ruleset](rules/fieldwire-rules.yml)

### Vocabulary

- [Fieldwire Vocabulary](vocabulary/fieldwire-vocabulary.yml)

### Examples

- [Create Task](examples/fieldwire-create-task-example.json)

### Commercial artifacts

- [Plans / Pricing](plans/fieldwire-plans-pricing.yml)
- [Rate Limits](rate-limits/fieldwire-rate-limits.yml)
- [FinOps Definition](finops/fieldwire-finops.yml)

## Maintainers

**FN:** Kin Lane

**Email:** info@apievangelist.com
