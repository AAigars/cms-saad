# Data Isolation for Complaint Management System

## Context and Problem Statement

The Complaint Management System is designed as a multi-tenant application, meaning multiple client organizations (tenants) will utilize the same application instance. One of our most critical non-functional requirements is data isolation. We must ensure that a tenant is only able to access their own data. Therefore we need a strategy that enforces this isolation strictly.

## Considered Options

1. Database per Tenant — Each tenant has their own physically separate database instance.

2. Schema per Tenant - One database but each tenant has their own schema.

3. Shared Schema with RLS: All tenants share tables with a `tenant_id` column which will utilise Row Level Security to enforce isolation at database level.

## Decision Outcome

Chosen option: "Shared Schema with RLS", because it provides robust security enforcement at a database level. This mitigates any risk from the application level leaking the data caused by application bugs or developer oversight. Additionally, opting for a shared schema reduces complexity by allowing us to keep a consistent schema between all tenants.

While the first option, database per tenant, provides complete isolation between other tenants, there is much higher complexity in developing and deploying the infrastructure compared to our chosen approach.

And lastly the second option, schema per tenant, does not provide isolation of the data at a database level which leaves the possiblity of data leaks from the application layer due to application bugs or developer oversight.

### Consequences

- Good, security is enforced at database level which ensures that application bugs or developer oversight will not leak any data.

- Good, single database and schema will ensure simplicity with our current tech stack compared to the other approaches.

- Bad, performance overhead as RLS adds a processing overhead to every query as the database must evaluate the policy.
