```mermaid
sequenceDiagram
    participant browser
    participant server

    browser ->> server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server ->> browser: URL redirect
    deactivate server

    browswer ->> server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server ->> browser: HTML document
    deactivate server

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server ->> browser: the css file
    deactivate server

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server ->> browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches JSON file from the server

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server ->> browser: [{"content":"dfadf","date":"2023-02-22T16:23:32.860Z"}...
    deactivate server

    Note right of browser: The browser executes the callback function that renders notes

    browser ->> 


```