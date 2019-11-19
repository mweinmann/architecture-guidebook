# [Product] Guidebook

A product guidebook provides supplementary documentation of a software system (project)
that is not easily reasoned from the code base. It should be kept current as the 
product evolves.

For new projects, a skeleton version of the guidebook can serve as the starting architecture
design document.

The primary authors and maintainers of the product guidebook are the software engineers 
responsible for building the product. While the primary audience is the current future team
members, the document should be accessible to the entire organization. To this end, the use
of technical jargon and acronyms should be minimized and defined on first use.

## System Context <a name="system_context"></a>

Provide high-level introduction to how the product fits into the SSC ecosystem.

The system context should answer the following:
* What is actually being built (e.g. web-app, data processor, etc.)?
* What are the high-level goals of the product?
* Who are the users of the product (including other products/systems within the ecosystem)?

Include a system context diagram that includes the following:
* Users and other products that interact with the product under consideration
* External resources shared with other systems (e.g., databases, S3 buckets, message queues, etc.)
  - To avoid clutter, omit common monitoring and logging infrastructure systems such as 
     DataDog, Splunk, etc.
  - If the product under consideration talks to different "instances" of an external resource
    (e.g., S3 buckets, RDS schema), it is usually better to have each "instance" as a distinct 
    entity on the system context diagram.
* Connect systems/users with directed arrows.
  - Include labels describing the nature of the connection.
  - For connection to data stores and queues, have the arrow show the direction that the data 
    is moving (readers will assume that it is the product and not the database, etc. that is
    initiating the request).
  - If the system diagram includes human users or systems outside of the SSC ecosystem, include a 
    boundary box that identifies the portion of SSC ecosystem included in the diagram.

## Functional Overview

Provide more details about what the product actually does. That is, the high-level functional requirements. Include the description of the key scenarios, use cases, or user stories. In contrast to the [System Context](#system_context), which explains how the product fits into the SSC ecosystem, this section provides more details into what the product actually does.

1. Use Case #1 summary
2. Use Case #2 Summary

## Quality Attributes

Summary of the non-functional requirements that influence the design of the product. If listed, need to be measurable and verifiable.

Non-functional requirements that should be considered (not exhaustive and not every item is relevant to every product):

### Performance
  - Response Time (time it takes between a request being sent and a response being received)
  - Latency (time it takes for a message or event to move through the system)
  - Processing windows 
### Scalability
  - How many concurrent users or events should the system support on average? Peak?
  - Data set size, including expected future growth.
### Availability
  - How much system downtime can we tolerate?
  - Criticality of failure (e.g., do we need on-call for off-hours)
### Security
  - Authentication
  - Authorization
  - Data confidentiality (including transit and storage)
### Management
  - Runtime topology
  - Feature flags
### Disaster Recovery
### Monitoring
  - Key metrics written to DataDog with expected and alert thresholds.
  - Include link to DataDog dashboard with key metrics
### Legal and Compliance
### Auditing
### Data Retention
### Accessibility
### Internationalization / Localization
### Constraints
  - Organization or technical constraints that must be followed.

## Architecture

This section provides an overview of how the product is organized to meet the functional and non-functional requirements.

### Design Decisions

Link to directory with decision decisions created from [ADR Template](adr-template.md)

### Deployment

Describe overall architecture from a deployment perspective. Provide diagram(s) and descriptions of all major components that make up the product solution. 

### Key Scenarios

Document key or representative sequences. Not every use case need be documented, but enough for readers to understand and evaluate the solution.

Create a sub-section for each scenario. 

#### Scenario 1

* Include appropriate diagrams (e.g., sequence, activity)
* Add description for complex processing and algorithms

## Data Model

Document key entities. Include any special data handling requirements

## API 

If application has APIs, they should be documented. Preferably as a link to a swagger YAML file.

