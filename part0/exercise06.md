```mermaid

sequenceDiagram 

participant BROWSER 
participant SERVER

BROWSER->>SERVER: GET https://studies.cs.helsinki.fi/exampleapp/spa
activate SERVER
SERVER-->>BROWSER: Html document
deactivate SERVER

BROWSER->>SERVER: GET https://studies.cs.helsinki.fi/exampleapp/main.css
activate SERVER
SERVER-->>BROWSER: CSS document
deactivate SERVER

BROWSER->>SERVER: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
activate SERVER
SERVER-->>BROWSER: JS document
deactivate SERVER
Note right of BROWSER: The browser starts executing the JavaScript code that fetches the JSON from the server

BROWSER->>SERVER: GET https://studies.cs.helsinki.fi/exampleapp/data.json
activate SERVER
SERVER-->>BROWSER: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
deactivate SERVER

Note right of BROWSER: The browser executes the callback function that renders the notes
Note right of BROWSER: The user submits the form. JS adds the new note to the local list and rerenders it immediately
BROWSER->>SERVER: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
activate SERVER
SERVER-->>BROWSER: 201 Created
deactivate SERVER