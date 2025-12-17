# Session Management Strategy for Complaint Management System

## Context and Problem Statement

We need to select a session management strategy that will securely identify and authenticate users between the presentation and application layer. The chosen mechanism must integrate seamlessly with our architecture and adhere to the non-functional requirements regarding maintainability and infrastructure simplicity.

## Considered Options

1. JSON Web Tokens — A client-side strategy where the server issues a signed token containing user data. The token is sent with every request and verified.

2. Server-Side Sessions — Traditional approach where Session Id is stored in a cookie and the session data is stored on the server (e.g. Redis)

3. Basic Authentication — Sending the username and password with every request (Base64 encoded)

## Decision Outcome

Chosen option: "JSON Web Tokens", because it allows us to implement a secure, stateless authentication system that stricly adheres to our requirements for maintainability and minimal infrastructure complexitiy. By utilising JWT's we eliminate the need of a dedicated session store like Redis which reduces the complexity and overhead of the implementation.

While the second option, server-side sessions, is a industry standard and proven to be a reliable option, it would require us to have a dedicated session store like Redis which will add too much complexity to the system especially for a proof-of-concept.

And lastly the third one, basic authentication, has significant security vulnerabilties, for example, credentials are sent in base64 encoding which can easily be decoded and can potentially be intercepted and does not offer any advantage over the other options.

### Consequences

Good, we avoid the complexity and cost of the other solutions which might require dedicated session stores like Redis.

Good, since the session sate is contained within a token on the client-side, the backend remains stateless which allows for easy scaling.

Bad, not possible to easily invalidate session tokens compared to other solutions like the second option as they have a set expiry.
