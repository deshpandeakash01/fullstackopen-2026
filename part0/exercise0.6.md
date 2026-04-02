sequenceDiagram
    participant browser
    participant server

    Note right of browser: User types note and clicks Save
    Note right of browser: JS handler prevents default form submit
    Note right of browser: JS adds note to local list and rerenders UI

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note right of browser: Content-type: application/json
    server-->>browser: 201 Created (JSON confirmation)
    deactivate server
