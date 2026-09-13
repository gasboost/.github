<div align="center">

<img src="https://github.com/user-attachments/assets/11e09588-b6d5-44c1-af06-ac573342e86b" width="320" alt="gasboost logo" />

# gasboost

### The modern TypeScript ecosystem for Google Apps Script.

Build production-grade applications on Google Apps Script with modern TypeScript tooling, structured application architecture, authentication, authorization, data access, testing, and realtime synchronization.

**Keep Google Workspace at the center. Modernize everything around it.**

[Repositories](https://github.com/orgs/gasboost/repositories)

</div>

---

## Why gasboost?

Google Apps Script is one of the simplest ways to build applications deeply integrated with Google Workspace.

Google Sheets, Drive, Gmail, Calendar, and other Workspace services are available directly from the runtime, making Apps Script especially powerful for internal tools, business applications, automation, and digital transformation.

But applications often grow beyond small scripts.

As they grow, developers need capabilities such as:

- structured application APIs
- type-safe client communication
- authentication and session management
- row-level authorization
- structured data access
- local testing
- modern frontend tooling
- realtime synchronization

**gasboost provides these missing pieces without replacing Google Apps Script.**

Apps Script remains the runtime and the bridge to Google Workspace.

gasboost builds a modern application development ecosystem around it.

<br />

<div align="center">
<img src="https://github.com/user-attachments/assets/9abc55eb-8366-4385-b302-edb77fafda68" width="900" alt="gasboost concept" />
</div>

<br />

## Ecosystem

gasboost is composed of focused packages that can be used independently or combined as a complete application stack.

### Application

Build structured backend applications and communicate with the frontend through type-safe APIs.

- Application endpoints
- GET / POST handling
- Type-safe RPC
- Client integration
- React integration
- Vite-based development

### Data

Build structured data access on top of Google Sheets.

- Type-safe queries
- Google Sheets ORM
- Filtering and sorting
- Relations and joins
- Transactions
- Migrations
- Constraints
- Replication

### Security

Treat authentication and authorization as first-class application concerns.

- Authentication
- Session management
- Multiple authentication methods
- Row Level Security
- Shared authorization policies

### Testing

Develop and test Apps Script-dependent code locally.

- In-memory Apps Script implementations
- Node.js implementations of Apps Script APIs
- Unit testing
- Integration testing
- Vitest-friendly workflows

### Realtime

Google Apps Script is not designed to be a realtime data delivery platform.

When realtime synchronization is required, gasboost can complement Apps Script with Firebase Realtime Database while keeping Google Sheets and Google Workspace at the center of the application.

Replication and Row Level Security make it possible to synchronize data without duplicating application authorization rules.

## Architecture

A typical gasboost application can look like this:

```text
React
  │
  ▼
Type-safe Client
  │
  ▼
Application Runtime
  │
  ├── Authentication
  ├── Row Level Security
  ├── Business Logic
  │
  ├── Google Workspace
  │     ├── Gmail
  │     ├── Calendar
  │     ├── Drive
  │     └── Sheets
  │
  └── Data Layer
        ├── Query
        ├── Sheet ORM
        └── Replica
              │
              ▼
        Firebase Realtime Database
```

Each technology keeps a clear responsibility.

**Google Apps Script**  
Application runtime and Google Workspace adapter.

**Google Sheets**  
Primary datastore for applications that benefit from direct Workspace integration.

**Firebase Realtime Database**  
Realtime synchronization layer when Apps Script alone is not sufficient.

**gasboost**  
The application-development layer that connects them with a consistent TypeScript architecture.

## Philosophy

### Keep Google Workspace at the center

gasboost does not try to turn Apps Script into Node.js.

The direct integration between Apps Script and Google Workspace is one of its greatest strengths.

gasboost preserves that advantage while improving the application architecture around it.

### TypeScript first

Application contracts, data structures, queries, authentication, authorization, and client communication should be type-safe wherever practical.

### Small packages, one ecosystem

Each package has a focused responsibility.

Applications can use only the parts they need while still benefiting from a consistent architecture across the ecosystem.

### Local development should feel normal

Apps Script applications should be testable and developable using familiar TypeScript tooling.

### Use the right infrastructure for the right responsibility

Apps Script should handle what Apps Script is good at.

External infrastructure should only be introduced where it provides a clear capability that Apps Script itself does not.

## Getting Started

gasboost is designed so developers should not need to understand the internal package structure before building an application.

The recommended entry point will be the gasboost project generator:

```bash
pnpm create gasboost
```

Instead of asking which internal packages to install, the generator is designed around application decisions such as authentication, datastore, authorization, realtime synchronization, and frontend architecture.

Until the project generator is available, explore the individual repositories for installation instructions and package-specific documentation.

## What can you build?

gasboost is intended for applications that need more structure than a small standalone script.

Examples include:

- internal business applications
- CRM and sales management systems
- reservation and scheduling systems
- approval workflows
- Google Workspace automation
- secure multi-user applications
- data-driven applications backed by Google Sheets
- realtime applications
- applications combining Google Workspace and external services

## Vision

Google Apps Script already provides one of the shortest paths from an idea to an application deeply integrated with Google Workspace.

Our goal is to make the development experience around it just as capable.

> **Make modern Google Apps Script development a first-class way to build real applications.**

## Community

gasboost is open source.

Issues, discussions, documentation improvements, examples, integrations, and code contributions are welcome.

If you build something with gasboost, we would love to hear about it.

---

<div align="center">

**Build modern applications on Google Apps Script.**

MIT License

</div>
