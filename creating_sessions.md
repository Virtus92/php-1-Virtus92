## How to create and access sessions
Every sub-page of a site that uses sessions should call **session_start()**.
If the user does not have a session, it starts one for them; if they do, it gets the session data and puts it in the $_SESSION superglobal array.

When a visitor first requests a page that calls **session start()**, a new session ID, session cookie, and session file are created.

If you add data to the **$_SESSION** superglobal array, when the page has finished running, the PHP interpreter adds the data to the session file for that user.

When collecting data from the **$_SESSION** superglobal array, the function must be called before any content is sent to the browser because it sends an HTTP header. It must also be called before the page tries to get session data, as it transfers data from the session file to the $_SESSION superglobal array.

```php
session_start();
```
The syntax to add data to the array is the same as for any associative array. The key should describe the data that the element is being used to store:
```php
$_SESSION['name'] = 'Ivy';
$_SESSION['age'] = 27;
```
Use the null-coalescing operator in case values are missing
```php
$name = $_SESSION['username'] ?? null;
$age = $_SESSION['age'] ?? null;
```
| Function | Description |
|-------|-------------|
| session_start() | Create new session, or get data from existing session. |
| session_set_cookie_params() | Settings used to create the session cookie. |
| session_get_cookie_params() | Returns an array holding the arguments used to set the cookie. |
| session_regenerate_id() | Create a new session ID, and update the session file and cookie. |
| session_destroy | Deletes the session file from the server. |

### Session Example

```php
<?php
//sessions.php -> current file
session_start();                      // Create/resume session
$counter = $_SESSION['counter'] ?? 0; // Get data
$counter = $counter + 1;              // Counter + 1
$_SESSION['counter'] = $counter;      // Update session

$message = 'Page views: ' . $counter; // Message
?>
<?php include 'includes/header.php'; ?> 
<h1>Welcome</h1>
<p><?= $message ?></p>
<p><a href="sessions.php">Refresh this page</a> 
to see the page views increase.</p>
<?php include 'includes/footer.php'; ?> 
```
