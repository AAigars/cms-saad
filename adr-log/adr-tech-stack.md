# Tech Stack for Complaint Management System

## Context and Problem Statement

We need to select a tech stack that will satisfy the functional scope, non-functional requirements and three-tier architecture for the Complaint Management System. The chosen stack must enable us to build a modern, user-friendly and accessible frontend, a highly scalable and secure backend, and an isolated data layer per tenant.

## Considered Options

1. Next.JS + Nest.JS + Drizzle — Modern tech stack, end-to-end type safety. Next.JS for client, Nest.JS for backend, and Drizzle ORM for database interaction.

2. Next.JS + Express.JS + Mongoose — MERN tech stack, very common flexible stack. Next.JS for client, Express.JS for backend, and Mongoose ORM.

3. Next.JS + Spring Boot / .NET Core — Next.JS for client but leveraging an enterprise ecosystem for the backend, such as Java (Sprint Boot) or C# (.NET Core)

## Decision Outcome

Chosen option: "Next.JS + Nest.JS + Drizzle", because this stack provides end-to-end type safety, which significantly reduces runtime errors and improves developer productivity. The consistency of using a single language (TypeScript) across all three tiers is a major advantage.

- Presentation Tier — Next.JS is a mature, high-performance library for building modern, component-based and accessible user interface.

- Application Tier — Nest.JS is a scalable framework. It's modular architecture is a perfect fit for our "Three-Tier Architecture" decision and is built to handle enterprise-grade, high-scale applications. It enforces a solid structure out of the box.

- Data Tier — Drizzle is a lightweight, modern, and type-safe ORM that integrates seamlessly with Nest.JS and PostgreSQL, providing strong type gurantees from the database schema all the way to the presenation tier.

The stack was chosen over the second option because Nest.JS provides a robust architectural foundation for a large-scale application.

And lastly, the third option was not considered to simplify development and avoid complexity of utilising multiple languages.

### Consequences

- Good, because end-to-end type safety from the data tier to presentation tier reducing possibility of bugs.

- Good, because using a single language (TypeScript) across entire stack simplifies the development process.

- Good, because Nest.JS enforces a strict architecture style to follow ensuring good development practises.

- Bad, because Nest.JS and Drizzle ORM are newer technologies than Express or Sprint Boot. This may mean less community-support ecosystem and steeper learning curve.
