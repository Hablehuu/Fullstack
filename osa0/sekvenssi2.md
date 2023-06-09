sequenceDiagram

    participant browser
    participant server
    
    Note browser updated the notes before sending it to the server
    preventDefault
    notes.push(note)
    redrawNotes()
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    Note server saves the body of the request
    push.(req.body.note,new Date())
    server-->>browser: 201 created
    deactivate server
