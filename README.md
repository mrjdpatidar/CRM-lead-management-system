# CRM — Lead Management & Distribution System

A web-based CRM connecting lead imports, agent allocation, interaction history, and follow-up tracking in one application.

**Developer:** Jagdish Patidar  
**Company:** Drunall Technologies  
**Project type:** Sales CRM & Lead Distribution Software  
**Repository type:** Public product case study  
**Source code:** Private  

[Visit the CRM Portal](https://crm.jdpatidar.com/)

> This repository contains product documentation only. The live application requires authorized access.

## Overview

This CRM supports sales organizations, call centers, and telemarketing teams that manage leads across multiple agents.

Administrators can import lead batches, map incoming spreadsheet columns, distribute records, and configure agent permissions. Agents can work with assigned leads, record call outcomes, and maintain interaction history.

The application uses Laravel and MySQL, with a Blade-based interface and server-side DataTables for lead browsing and filtering.

## Business Challenge

Managing leads through separate spreadsheets makes it difficult to maintain clear ownership and consistent follow-up records.

Common operational needs include:

- Importing leads from files with different column names.
- Distributing records across active agents.
- Identifying leads that have not been contacted.
- Recording repeated outreach attempts.
- Reviewing call outcomes and follow-up details.
- Restricting editing, deletion, and upload permissions.
- Tracking imports and user activity.

The CRM brings these activities into a shared workflow.

## My Contribution

I developed the application around lead allocation and daily agent operations.

The implementation includes:

- Administrator and agent interfaces.
- CSV import and dynamic column mapping.
- Lead distribution and bulk updates.
- Call response logging and interaction history.
- Automatic touchpoint tracking.
- Server-side lead filtering.
- Configurable agent permissions.
- Account activity and subscription controls.

## Core Features

### 1. Lead Imports & Column Mapping

Administrators can import lead records from CSV files without requiring identical source column names.

The import workflow supports:

- File upload and column inspection.
- Mapping headers to lead fields.
- Contact information, city, and source mapping.
- Assignment of imported leads to agents.
- Batch identifiers for upload history.

### 2. Lead Distribution

Lead allocation supports distributing records across active sales agents.

- Assign records manually.
- Distribute leads evenly or using custom allocation counts.
- Review records assigned to a specific agent.
- Perform supported bulk edits and reassignment operations.

This connects imported batches with clear agent ownership.

### 3. Call Logging & Interaction History

Agents can record interactions directly from the lead interface.

Interaction records include:

- Call outcome.
- Call or follow-up date and time.
- Duration.
- Notes and response comments.
- Whether additional details were shared.
- Whether a group link was shared.

The sharing fields record agent activity; they do not imply an automated WhatsApp or email integration.

### 4. Call Outcomes

Documented response categories include:

- No Pick Call.
- Switched Off.
- Interested.
- Not Interested.
- Busy.
- Call Back.
- Not Reachable.
- Advisor.
- Broker.
- Call Cut.
- Invalid Number.
- Existing Client.

These outcomes help agents and administrators organize follow-up work.

### 5. Automatic Touchpoint Tracking

Newly imported leads begin as untouched.

When an agent logs an interaction, the application advances the lead's touchpoint status.

This allows teams to distinguish:

- Leads with no recorded contact.
- Leads contacted once.
- Leads with multiple recorded interactions.

Touchpoint count describes outreach activity rather than a complete sales deal pipeline.

### 6. Advanced Lead Filtering

The lead interface uses AJAX-based server-side DataTables.

Documented filters include:

| Filter | Purpose |
| --- | --- |
| Date range | Review records by creation or modification dates |
| Assigned agent | Review an agent's leads from the admin interface |
| Touched | Find leads with recorded interactions |
| Untouched | Find leads without recorded interactions |
| Today's interactions | Review leads contacted today |
| Call outcome | Find leads with selected response categories |
| Lead source | Filter by recorded acquisition source |

Server-side processing handles table requests without loading the complete lead dataset into the browser at once.

### 7. Agent Permissions

Administrators can configure access for individual agents.

| Permission | Capability |
| --- | --- |
| Edit | Update assigned lead information |
| Delete | Delete selected leads |
| Activity | View personal activity and upload history |
| Lead upload | Import individual lead CSV files |
| Restricted access | View assigned records and log calls |

The application separates administrator and agent workflows.

### 8. Authentication & Account Status

Account functionality includes:

- Role-based login.
- Active and inactive account controls.
- Profile updates.
- Password recovery.
- Login and logout activity records.

### 9. Upload & Activity History

Batch identifiers connect imported records with upload history.

Activity records support reviewing lead uploads and user login/logout events.

### 10. Subscription Controls

The application includes subscription validity checks.

- Display a warning near subscription expiry.
- Restrict access when a subscription is expired or inactive.
- Return appropriate responses for page and AJAX requests.

## Technology Stack

The following stack is documented for this project.

| Layer | Technologies |
| --- | --- |
| Backend | PHP, Laravel 8 |
| Architecture | Model-View-Controller |
| Database | MySQL / MariaDB |
| Templates | Laravel Blade |
| Styling | Bootstrap 4, custom CSS |
| JavaScript | jQuery |
| Lead Tables | DataTables, DataTables Buttons |
| Spreadsheet Processing | Laravel Excel |
| Asset Tooling | Laravel Mix |

## Architecture Overview

The CRM uses a server-rendered Laravel application with AJAX requests for lead table data.

- **Presentation:** Blade templates, Bootstrap, and JavaScript.
- **Access control:** Authentication, account status, roles, and subscription middleware.
- **Application logic:** Lead imports, allocation, response logging, and user management.
- **Persistence:** MySQL records for users, leads, interactions, activities, and subscriptions.

## Example Workflows

### Import & Allocate Leads

1. Upload a CSV file.
2. Inspect the available columns.
3. Map columns to the CRM's lead fields.
4. Select agents and allocation counts.
5. Save the imported batch.
6. Review assigned records and upload history.

### Record a Sales Interaction

1. Open an assigned lead.
2. Review available interaction history.
3. Select the call outcome.
4. Record notes, duration, and relevant follow-up details.
5. Save the response.
6. Review the updated touchpoint status.

### Review Daily Outreach

1. Filter leads by today's interactions.
2. Narrow results by agent, source, or call outcome.
3. Review recorded responses.
4. Identify records needing further follow-up.

### Configure an Agent

1. Create or update the agent account.
2. Set the account's active status.
3. Configure editing, deletion, activity, and upload permissions.
4. Allocate the appropriate leads.

## Engineering Considerations

### Flexible Import Formats

Dynamic column mapping accommodates CSV files from different lead sources.

### Assignment & Access

Agent ownership and configurable permissions organize access to operational records.

### Interaction History

Separate response records preserve multiple interactions for the same lead.

### Filtered Data Retrieval

Server-side table processing supports filtered browsing without transferring the full dataset on each page load.

### Batch Traceability

Upload identifiers connect imported leads with batch history and related activity records.

## Functional Outcomes

The CRM provides:

- Centralized lead records.
- Agent-based lead ownership.
- Flexible CSV imports.
- Structured call logging.
- Visibility into contacted and untouched leads.
- Filtering for daily follow-up work.
- Configurable agent permissions.
- Upload and account activity history.

No quantified conversion, productivity, or performance improvement claims are presented in this case study.

## Live Portal

[Open the CRM Portal](https://crm.jdpatidar.com/)

Access requires an authorized account. Contact us to discuss a guided walkthrough.

## Repository Scope

This public repository contains case study documentation only.

It does not include application source code, lead data, customer contact information, database exports, credentials, or deployment configuration.

The application source code remains private.

## About the Developer

**Jagdish Patidar**  
Founder & CEO — **Drunall Technologies**

I build eCommerce experiences, custom business applications, and workflow automation with a focus on reliability and maintainability.

- [Drunall Technologies](https://www.drunall.com)
- [Portfolio](https://jdpatidar.com)
- [LinkedIn](https://www.linkedin.com/in/jdpatidar/)

> Understand the business first, choose the technology second, and don’t confuse a working demo with a finished product.
