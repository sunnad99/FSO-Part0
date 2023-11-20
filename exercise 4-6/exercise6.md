sequenceDiagram
	participant browser
	participant server
	
	Note right of browser: Sending the note in the body of the HTTP request: this code rocks!
	browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
  activate server
  server-->>browser: JSON Response: {"message":"note created"}
  deactivate server

	Note right of browser: 1. On submitting, the default redirect behavior is prevented
	Note right of browser: 2. A note is crafted on the client side and stored on the client side before rerendering all of them
	Note right of browser: 3. Once the notes are redrawn, the note is sent to the server through a POST request shown in the diagram above