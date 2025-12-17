# Architecture Style for Complaint Management System

## Context and Problem Statement

We need to select a architectural style that will define the structure of the Complaint Management System. The chosen style must clearly separate the user interface, business logic and data storage, to be able to adhere to our non-functional requirements of scalability (NFR01), performance (NFR02) and maintainability.

## Considered Options

1. Three-Tier Architecture — Pattern that physically and logically separates the system into a Presentation Tier (UI), and Application Tier (business logic), and a Data Tier (database).

2. Microservice Architecture — Pattern where the backend is composed of multiple independently deployable services which is designed for high scalability and flexibility.

3. Layered Architecture — Pattern where code is seperated logically within a single application.

## Decision Outcome

Chosen option: "Three-Tier Architecture", becaues it provides the clearest and most appropriate high-level structure for the project by clear separation of presentation tier, application tier, and a data tier which will adhere to the non-functional requirements of scalibility (NFR01), performance (NFR02) and maintainability.

While the second option, microservice architecture, is a powerful pattern for scalability, it introduces significant complexity in the development, deployment and management, which is not ideal for the proof-of-concept.

And lastly the third option, layered architecture, does not describe the high-level seperation between the frontend, backend and database.

### Consequences

- Good, because creates a strong, clear seperation of logic, which improves maintainability.

- Good, presentation tier and data tier can't communicate directly, a well-designed application tier will ensure that we can secure the data easily.

- Bad, because the model is not as scalable as a pure microservice architecture, but it's the right trade-off for the project's scope.

## References

Three-Tier Architecture: https://www.ibm.com/think/topics/three-tier-architecture
