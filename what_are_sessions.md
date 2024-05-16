# Sessions

Sessions store information about a user and their preferences on the server. They are called sessions because they only store the data for the duration of a single visit to the site.

## What is a session?

When a session starts, the PHP interpreter creates three things:
- A **session ID**, a string used to identify an individual visitor.
- A **session file**, which is a text file that is stored on the server. It is used to hold data about that user. Its filename will contain the session ID
- A **session cookie**, which is stored in the browser. Its name is PHPSESSID and its value is the user's session ID.

## How long does a session last?
To work, a session needs both the session cookie in the browser and the session file on the server.

- Session cookies expire when users close the browser.
- Session files can be deleted by the server if they are not modified within a period (the default is 24 minutes).

## Getting session data
If a browser has a session cookie, it is sent to the server every time the user requests another page from that site. The session ID is used to identify the user so that the server can:

- Find the session file whose filename contains the session ID sent in the cookie.
- Take data from the session file and put it into the $_SESSION superglobal array so the page can access it.

## Saving session data
Once a session has been created, new data can be saved to the user's session by adding it to the $_SESSION superglobal array.

When a page has finished running, the PHP interpreter takes all of the data from the $_SESSION superglobal array and saves it in that user's session file. Saving data to the session file updates its last modified time, and the PHP interpreter can check this time to tell if a session was used recently.

## How long sessions last
To work, a session needs both the session cookie in the browser and the session file on the server.

- Session cookie expires when users close the browser
- Session files can be deleted by the server if they are not modified within a time period (the default is 24 minutes).

## How sessions are started
When a site uses sessions, every page should call PHP's built-in **session_start()** function. When the function is called, if the browser requesting the page did not send a session cookie or if a matching session file cannot be found, the PHP interpreter automatically starts a new session for that user.
