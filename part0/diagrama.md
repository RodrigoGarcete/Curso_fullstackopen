```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes
```

### 0.4 Diagrama de nota

```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: The note is written in the input.
    Note right of browser: Click on the form button


    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_notes
    server-->>browser: Response 302 Found
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    server-->>browser: HTML document
    
    Note right of browser: It repeats like the example diagram, as it is interpreted as a page reload.
```

### 0.5 Diagrama de aplicación de una sola página
```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: It is similar to the previous case

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes
```

### 0.6: Nueva nota en diagrama de aplicación de una sola pagina

```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: The note is written in the input.
    Note right of browser: Click on the form button

    Note right of browser: Send POST via ajax


    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_notes
    server-->>browser: Response 200

    Note right of browser: The page does not reload and the note is inserted directly into the list
   
    
    
```