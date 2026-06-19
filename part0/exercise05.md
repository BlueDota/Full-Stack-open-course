```mermaid

sequenceDiagram 

participant BROWSER 
participant SERVER

BROWSER->>SERVER: GET https://studies.cs.helsinki.fi/exampleapp/spa
activate SERVER
SERVER-->>BROWSER: Html document
deactivate  SERVER

BROWSER->>SERVER: GET https://studies.cs.helsinki.fi/exampleapp/main.css
activate SERVER
SERVER-->>BROWSER: CSS document
deactivate  SERVER

BROWSER->>SERVER: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
activate SERVER
SERVER-->>BROWSER: JS document
deactivate  SERVER

BROWSER->>SERVER: GET https://studies.cs.helsinki.fi/exampleapp/data.json
activate SERVER
SERVER-->>BROWSER: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
deactivate  SERVER