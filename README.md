# Fieldwire (fieldwire)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/fieldwire/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/fieldwire/refs/heads/main/apis.yml)

## Scope

- **Access:** 3rd-Party

## Tags

- Construction
- Construction Technology
- ConTech
- Field Management
- Punch List
- Plans
- Drawings
- BIM
- Forms
- Inspections
- Project Management
- Hilti

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Fieldwire Account API

Account-scoped (super) endpoints used to authenticate, exchange the long-lived API key for a short-lived JWT access token, and manage account-level users, roles, attachments, data types, custom stamps, form templates, and project transfers. Calls hit the global super host at https://client-api.super.fieldwire.com before regional project APIs.

- **Human URL:** [https://developers.fieldwire.com/docs/getting-started](https://developers.fieldwire.com/docs/getting-started)

#### Tags

- Account
- Authentication
- Construction
- Users

#### Properties

- [Documentation](https://developers.fieldwire.com/docs/getting-started)
- [Documentation](https://developers.fieldwire.com/docs/authentication)
- [OpenAPI](openapi/fieldwire-account-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fieldwire-account-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fieldwire-account-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fieldwire Projects API

Create, retrieve, update, archive, transfer, and synchronise construction projects across the Fieldwire account. Includes project statistics, notifications, project teams, project users, permissions, and project-level forms / templates. Project data is region-resident — US clients call client-api.us.fieldwire.com/api/v3, EU clients call client-api.eu.fieldwire.com/api/v3.

- **Human URL:** [https://developers.fieldwire.com/reference/get_projects_in_account](https://developers.fieldwire.com/reference/get_projects_in_account)

#### Tags

- Construction
- Projects
- Field Management

#### Properties

- [Documentation](https://developers.fieldwire.com/reference/get_projects_in_account)
- [OpenAPI](openapi/fieldwire-projects-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fieldwire-projects-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fieldwire-projects-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fieldwire Tasks API

Create and manage construction tasks — punch list items, RFIs-as-tasks, inspections, and work assignments — including check items, task relations, task types, custom task attributes, bubbles (comments, photos, video, attachments), and template checklists with up to 500 check items per task.

- **Human URL:** [https://developers.fieldwire.com/reference/get_tasks_in_project](https://developers.fieldwire.com/reference/get_tasks_in_project)

#### Tags

- Construction
- Field Management
- Tasks
- Punch Lists

#### Properties

- [Documentation](https://developers.fieldwire.com/reference/get_tasks_in_project)
- [Documentation](https://developers.fieldwire.com/docs/custom-task-attributes)
- [OpenAPI](openapi/fieldwire-tasks-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fieldwire-tasks-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fieldwire-tasks-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/fieldwire-task-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Fieldwire Plans and Sheets API

Upload PDF drawing sets, version sheets, organise floorplans into hierarchical collections, auto-extract sheet numbers / titles, manage hyperlinks and multi-hyperlinks between sheets, and attach Building Information Models with versioned object trees for calibration and 3D task creation.

- **Human URL:** [https://developers.fieldwire.com/docs/uploading-plans-via-api](https://developers.fieldwire.com/docs/uploading-plans-via-api)

#### Tags

- Construction
- Plans
- Sheets
- Drawings
- BIM

#### Properties

- [Documentation](https://developers.fieldwire.com/docs/uploading-plans-via-api)
- [Documentation](https://developers.fieldwire.com/docs/floorplan-collections-api-guide)
- [OpenAPI](openapi/fieldwire-plans-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fieldwire-plans-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fieldwire-plans-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fieldwire Forms API

Author account-level form templates, publish them to projects, capture form records and section inputs from the field, manage form statuses, signatures, markups, and form-level permissions. Used for daily reports, safety inspections, QA/QC checklists, and custom data collection in the field.

- **Human URL:** [https://developers.fieldwire.com/docs/working-with-project-forms](https://developers.fieldwire.com/docs/working-with-project-forms)

#### Tags

- Construction
- Forms
- Inspections
- Data Collection

#### Properties

- [Documentation](https://developers.fieldwire.com/docs/working-with-project-forms)
- [Documentation](https://developers.fieldwire.com/docs/getting-form-data)
- [OpenAPI](openapi/fieldwire-forms-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fieldwire-forms-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fieldwire-forms-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fieldwire Attachments and Media API

Upload, manage, and markup attachments — photos, videos, PDFs, spec sheets — using a two-step flow that returns short-lived signed AWS S3 POST tokens for direct browser-to-S3 upload. Markups support GeoJSON drawings, arrows, text, and measurement overlays, and can be flattened into image thumbnails.

- **Human URL:** [https://developers.fieldwire.com/reference/add_aws_post_tokens](https://developers.fieldwire.com/reference/add_aws_post_tokens)

#### Tags

- Construction
- Attachments
- Photos
- Files
- Media

#### Properties

- [Documentation](https://developers.fieldwire.com/reference/add_aws_post_tokens)
- [OpenAPI](openapi/fieldwire-attachments-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fieldwire-attachments-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fieldwire-attachments-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fieldwire Project Financials API

Manage project budget line items, actual costs, tier cost codes, and change orders for Business Plus customers. Exposes the project-financials surface that backs Fieldwire's budget management and change order workflows.

- **Human URL:** [https://developers.fieldwire.com/reference/get_budget_line_items_in_project](https://developers.fieldwire.com/reference/get_budget_line_items_in_project)

#### Tags

- Construction
- Budget
- Cost Management
- Change Orders
- Project Financials

#### Properties

- [Documentation](https://developers.fieldwire.com/reference/get_budget_line_items_in_project)
- [OpenAPI](openapi/fieldwire-financials-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fieldwire-financials-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fieldwire-financials-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fieldwire RFIs and Submittals API

Track Requests for Information, submittals, submittal types, spec sections, attachments, markups, watchers, approvals, and submittal log extraction. Supports email-based responses, ball-in-court reassignments, and renumbering with the lead company's own format.

- **Human URL:** [https://developers.fieldwire.com/reference/get_rfis_in_project](https://developers.fieldwire.com/reference/get_rfis_in_project)

#### Tags

- Construction
- RFIs
- Submittals
- Spec Sections
- Approvals

#### Properties

- [Documentation](https://developers.fieldwire.com/reference/get_rfis_in_project)
- [OpenAPI](openapi/fieldwire-rfis-submittals-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fieldwire-rfis-submittals-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fieldwire-rfis-submittals-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fieldwire Webhooks API

Subscribe to real-time event notifications for attachments, entity tags / taggings, floorplans, forms, hyperlinks, multi-hyperlinks, projects, project resource links, sheets, sheet uploads, tasks, task check items, and task relations. Per-subscription entity_filters (max 20) and project_filters (max 100) narrow the firehose.

- **Human URL:** [https://developers.fieldwire.com/docs/beta-creating-webhook-configurations](https://developers.fieldwire.com/docs/beta-creating-webhook-configurations)

#### Tags

- Construction
- Webhooks
- Events
- Realtime

#### Properties

- [Documentation](https://developers.fieldwire.com/docs/beta-creating-webhook-configurations)
- [Documentation](https://developers.fieldwire.com/docs/webhook-event-types)
- [Documentation](https://developers.fieldwire.com/docs/webhook-filters)
- [OpenAPI](openapi/fieldwire-webhooks-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fieldwire-webhooks-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fieldwire-webhooks-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [AsyncAPI](asyncapi/fieldwire-webhooks-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)

## Common Properties

- [Portal](https://www.fieldwire.com)
- [Documentation](https://developers.fieldwire.com)
- [Getting Started](https://developers.fieldwire.com/docs/getting-started)
- [Authentication](https://developers.fieldwire.com/docs/authentication)
- [Rate Limits](https://developers.fieldwire.com/docs/rate-limiting)
- [Documentation](https://developers.fieldwire.com/docs/pagination)
- [Documentation](https://developers.fieldwire.com/docs/filtering)
- [Versioning](https://developers.fieldwire.com/docs/versioning)
- [F A Q](https://developers.fieldwire.com/docs/frequently-asked-questions)
- [Changelog](https://developers.fieldwire.com/changelog)
- [R S S](https://developers.fieldwire.com/changelog.rss)
- [Changelog](https://www.fieldwire.com/changelog/)
- [Status Page](https://status.fieldwire.com/)
- [Support](https://help.fieldwire.com/hc/en-us)
- [Documentation](https://help.fieldwire.com/hc/en-us/articles/205097173-Introduction-to-the-Fieldwire-API)
- [Documentation](https://www.fieldwire.com/integrations/)
- [Documentation](https://www.fieldwire.com/integrations/fieldwire/api/)
- [GitHub Organization](https://github.com/Fieldwire)
- [SDK](https://github.com/Fieldwire/fieldwire_ruby_sample)
- [SDK](https://github.com/Fieldwire/fieldwire_java_sample)
- [Pricing](https://www.fieldwire.com/pricing/)
- [Plans](https://www.fieldwire.com/pricing/)
- [Documentation](https://www.fieldwire.com/about/)
- [Security](https://www.fieldwire.com/security/)
- [Privacy Policy](https://www.fieldwire.com/privacy/)
- [Terms of Service](https://www.fieldwire.com/terms/)
- [LinkedIn](https://www.linkedin.com/company/fieldwire)
- [Twitter](https://twitter.com/Fieldwire)
- [YouTube](https://www.youtube.com/@fieldwire)
- [Documentation](https://www.hilti.com)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
