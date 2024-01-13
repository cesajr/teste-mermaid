# teste-mermaid
```mermaid
sequenceDiagram
    participant browser
    participant server
    participant database

    Note right of browser: Usuário escreve uma nova nota no campo de texto

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/notes (new note data)
    activate server
    server-->>database: Save new note data
    activate database
    database-->>server: Confirmation
    deactivate database
    server-->>browser: Confirmation response
    deactivate server

    Note right of browser: Atualização da interface do usuário após criar a nota
```
```mermaid
graph TD
  subgraph Browser
    a[User]
    b[SPA Application]
  end

  subgraph Server
    c[API Endpoint - /api/notes]
    d[Database]
  end

  a -->|Interage com| b
  b -->|Requests data from| c
  c -->|Retrieves data from| d
  b -->|Updates UI| b
  b -->|Sends data to| c
  c -->|Saves data to| d
```
