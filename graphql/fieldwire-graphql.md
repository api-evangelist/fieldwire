# Fieldwire GraphQL Schema

This document describes a conceptual GraphQL schema for the Fieldwire construction management API. Fieldwire provides a REST API (https://developers.fieldwire.com/) covering projects, tasks, plans/sheets, forms, attachments, RFIs, submittals, financials, and webhooks. This GraphQL schema models the same domain as a unified graph.

## Source APIs

- Fieldwire Account API — authentication, users, roles, form templates
- Fieldwire Projects API — projects, teams, notifications, statistics
- Fieldwire Tasks API — tasks, check items, bubbles, task types, custom attributes
- Fieldwire Plans and Sheets API — floorplans, sheets, hyperlinks, BIM
- Fieldwire Forms API — form templates, form records, sections, signatures
- Fieldwire Attachments and Media API — photos, videos, PDFs, markups
- Fieldwire Project Financials API — budget line items, change orders, cost codes
- Fieldwire RFIs and Submittals API — RFIs, submittals, spec sections, approvals
- Fieldwire Webhooks API — webhook configurations, event subscriptions, filters

## Schema Overview

The schema exposes 62 named types covering the full Fieldwire domain:

### Core Project Types
- `Project` — top-level construction project with region, status, and statistics
- `ProjectDetails` — extended metadata including custom attributes and transfer state
- `ProjectStatus` — enum of active, archived, completed

### Plans and Sheets
- `Floorplan` — drawing set within a project
- `FloorplanDetails` — extended floorplan metadata including BIM links
- `FloorplanLevel` — hierarchical level within a floorplan collection
- `Sheet` — individual drawing sheet (PDF page or image)
- `SheetDetails` — sheet metadata including auto-extracted number and title
- `SheetRevision` — versioned revision of a sheet

### Tasks
- `Task` — punch list item, RFI-as-task, or work assignment
- `TaskDetails` — extended task fields including custom attributes
- `TaskStatus` — enum of open, in_progress, resolved, closed
- `TaskCategory` — project-defined category grouping tasks
- `TaskPriority` — enum of critical, high, medium, low

### Locations
- `Location` — named location pinned on a floorplan
- `LocationDetails` — extended location with area and associated tasks
- `LocationArea` — bounded region on a sheet used for spatial filtering

### Attachments and Media
- `Attachment` — photo, video, PDF, or file attached to a task or form
- `AttachmentDetails` — extended attachment fields including markup GeoJSON
- `AttachmentType` — enum of photo, video, pdf, file

### Forms
- `Form` — form record captured in the field
- `FormDetails` — extended form fields including signatures and section inputs
- `FormTemplate` — account-level form template
- `FormTemplateDetails` — template metadata including field definitions
- `FormField` — individual field definition within a form template
- `FormFieldDetails` — field type, options, and validation rules

### Checklists
- `Checklist` — template checklist associated with a task type
- `ChecklistDetails` — checklist metadata and item list
- `ChecklistItem` — individual check item in a checklist
- `ChecklistItemDetails` — check item with completion state and assignee

### Notes and Bubbles
- `Note` — text comment associated with a task or location
- `NoteDetails` — note with author, timestamp, and attachments
- `Hyperlink` — link between two sheets or external URL
- `HyperlinkDetails` — hyperlink with anchor point and target coordinates
- `Bubble` — comment, photo, video, or attachment pinned on a sheet
- `BubbleDetails` — bubble with position, author, and media
- `BubbleStatus` — enum of open, resolved

### Files and Folders
- `FolderNode` — node in the project file folder hierarchy
- `FileDetails` — file metadata including storage URL and MIME type

### Reports
- `Report` — generated project report (daily, safety, QA/QC)
- `ReportDetails` — report metadata including export URL and form references

### Teams and Users
- `Team` — team within a project or account
- `TeamDetails` — team membership and permission scope
- `User` — Fieldwire account user
- `UserDetails` — extended user profile including role and region assignments
- `UserRole` — enum of admin, standard, viewer, contractor

### Company and Account
- `Company` — company/organisation in the Fieldwire account
- `CompanyDetails` — company metadata including logo and contact info

### Access and Auth
- `Invite` — pending project or team invitation
- `InviteDetails` — invite with expiry, role, and sender
- `APIKey` — long-lived API key for account access
- `Token` — short-lived JWT access token

### Webhooks
- `Webhook` — webhook subscription configuration
- `WebhookEvent` — enum of entity event types (task.created, sheet.uploaded, etc.)

### Search
- `Search` — search query parameters
- `SearchResults` — paginated search results across entity types

### RFIs and Submittals
- `RFI` — Request for Information record
- `RFIDetails` — RFI with ball-in-court, responses, and attachments
- `Submittal` — submittal package record
- `SubmittalDetails` — submittal with spec section, approval chain, and attachments

### Financials
- `BudgetLineItem` — budget line item tied to a cost code
- `ChangeOrder` — change order record with status and amounts
- `CostCode` — tier cost code for budget categorisation

## Authentication

The Fieldwire API uses a two-step authentication flow. A long-lived API key (created in the account portal) is exchanged for a short-lived JWT access token via POST /api_keys/token. All subsequent requests pass the JWT as a Bearer token. Tokens expire and must be refreshed. In this GraphQL schema the `Token` type represents the JWT response and `APIKey` represents the long-lived credential.

## Regional Endpoints

Project data is region-resident. US projects use `client-api.us.fieldwire.com/api/v3` and EU projects use `client-api.eu.fieldwire.com/api/v3`. Account-level (super) endpoints use `client-api.super.fieldwire.com`. A GraphQL gateway would route queries to the correct regional endpoint based on the project's `region` field.

## Pagination and Filtering

The Fieldwire REST API uses cursor-based pagination via `last_synced_at` and `per_page` parameters. The GraphQL schema wraps list fields with a `Connection` pattern exposing `nodes` and `pageInfo`. The `filter` argument on list fields maps to Fieldwire's query-string filtering.

## References

- Developer Portal: https://developers.fieldwire.com/
- Getting Started: https://developers.fieldwire.com/docs/getting-started
- Authentication: https://developers.fieldwire.com/docs/authentication
- Rate Limiting: https://developers.fieldwire.com/docs/rate-limiting
- Webhooks: https://developers.fieldwire.com/docs/beta-creating-webhook-configurations
