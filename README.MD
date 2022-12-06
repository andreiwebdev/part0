0.4 New note diagram
<br /><br />

```mermaid
sequenceDiagram
    participant browser
    participant server
    browser->>server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note
    server->>browser: HTTP status code 302 URL redirect
```

note over browser: <br />
when the button on the form is clicked <br />
browser will send the user input to the server <br />
end note <br />


```mermaid
sequenceDiagram
    participant browser
    participant server
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
    server->>browser: html code
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
    server->>browser: css code
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
    server->>browser: javascript code
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
    server->>browser: raw data of the notes
```

note over browser:<br />
browser requests updated html code<br />
browser requests css code<br />
browser requests javascript code<br />
that requests JSON data from server <br />
end note<br />

0.5: Single page app diagram
<br /><br />

```mermaid
sequenceDiagram
    participant browser
    participant server
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa
    server->>browser: html code
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
    server->>browser: css code
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    server->>browser: javascript code
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
    server->>browser: notes data
```

0.6: New note in Single page app diagram
<br /><br />

```mermaid
sequenceDiagram
    participant browser
    participant server
    browser->>server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    server->>browser: HTTP status code 201 - updated notes list
```

note over browser:<br />
browser sends the user input to the server<br />
browser fetches notes data from the server<br />
end note<br />