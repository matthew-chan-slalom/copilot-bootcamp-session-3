# Cloud Architecture Overview

This document provides a simple system context view of the monorepo application.

## System Context Diagram

```mermaid
flowchart LR
    User[End User]
    FE[React Frontend\npackages/frontend]
    API[Express API\npackages/backend]
    STORE[(In-Memory Store\nRuntime Data)]

    User -->|Uses in browser| FE
    FE -->|HTTP JSON API calls| API
    API <--> |Read/Write tasks| STORE
```

## Create TODO Sequence

```mermaid
sequenceDiagram
    actor U as End User
    participant FE as React Frontend
    participant API as Express API
    participant S as In-Memory Store

    U->>FE: Enter TODO text and submit form
    FE->>API: POST /tasks { title, completed: false }
    API->>S: Create task in memory
    S-->>API: Return created task (id, title, completed)
    API-->>FE: 201 Created + task JSON
    FE-->>U: Show new TODO in task list
```

## Components

- React frontend: Single-page UI that renders tasks and sends API requests.
- Express API: Handles task endpoints and application logic.
- In-memory store: Process-local data storage used by the API (non-persistent).

## Notes

- The in-memory store resets when the backend process restarts.
- This architecture is suitable for learning and development, not production persistence.
