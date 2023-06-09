sequenceDiagram
  participant browser
  participant server

  browser->>server POST https://studies.cs.helsinki.fi/exampleapp/new_note
  activate server
  server->>browser: 302 redirect
  deactivate server

  browser->>server GET https://studies.cs.helsinki.fi/exampleapp/notes
  activate server
  server->>browser: raw HTML document
  deactivate server

  browser->>server GET https://studies.cs.helsinki.fi/exampleapp/main.css
  activate server
  server->>browser: CSS file
  deactivate server

  browser->>server GET https://studies.cs.helsinki.fi/exampleapp/main.js
  activate server
  server->>browser: javascript file returned
  deactivate server

  Note right of browser: the browser executes code and requests json file

  browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
  activate server
  server->>browser: note data
  deactive server