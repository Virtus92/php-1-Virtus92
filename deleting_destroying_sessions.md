# The life of a session
Browsers delete session cookies wehn the browser window is closed.
Servers delete session files when the garbage collection process runs. 
As a result, sessions can last longer than you expect them to.

## Simple logout
When the user logs out, the session and all enclosing data should be deleted.

Terminating a session involves the four steps below:
1. Remove all data from the session file, by setting the $_SESSION superglobal variable to a blank array. This also prevents any subsequent code in the same page from accessing those values.
```php
$_SESSION = [];
```
2. In Step 3 setcookie() will be used to update the session cookie. When it is used, the arguments for the path, domain, secure and httponly parameters must use the same values that were used when the cookie was created.

PHP's session_get_cookie_params() function will return the values that were used for these parameters when the session cookie was created. The values it returns are stored as an array in the $params variable.
```php
$params = session_get_cookie_params();
```
3. PHP's setcookie() function is used to update the session cookie.
The value parameter is set to a blank string; this deletes the session ID from the session cookie.

The expires parameter is set to a date in the past to stop the browser sending the cookie to the server, if it requests further pages, All of the other parameters are set using the values collected in Step 2 and stored as an array in the $params variable.
```php
setcookie('PHPSESSID', '', time() - 3600, $params['path'], $params['domain'],
        $params['secure'], $params['httponly']);  
```
4. Call PHP's session_destroy() function to tell the PHP interpreter to delete the session file. The PHP interpreter will delete the file immediately rather than waiting for garbage collection to delete it.
```php
session_destroy();
```

