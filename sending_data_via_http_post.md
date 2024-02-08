# How form data is sent to the server
Forms allow visitors to enter text and select options. For each form control, the browser can send a name and value to the server along with a page request.

The HTML form tag requires two attributes:
1. The value of the action attribute is the PHP file that the form data should be sent to.
2. The value of the method attribute indicates how to send the form data to the server

```html
//   *1 - page data should be sent to   *2 how the data should be sent
<form action="/some-form-handling-page.php" method="post">
    <ul>
        <li>
            <label for="name">Name:</label>
            <input type="text" id="name" name="user_name" />
        </li>
        <li>
            <label for="mail">Email:</label>
            <input type="email" id="mail" name="user_email" />
        </li>
        <li>
            <label for="msg">Message:</label>
            <textarea id="msg" name="user_message"></textarea>
        </li>
        <li class="button">
            <button type="submit">Send your message</button>
        </li>
    </ul>
</form>
```

The form above is sent via **HTTP POST**, so the browser will add the names and values of the form controls to the HTTP headers. The headers are sent with the request to **some-form-handling-page.php**. For each header:

- The **name** is the value of the **name** attribute of that form control.
- The **value** is the text the user entered or the value of the item they selected.

## Getting form data
When the PHP interpreter receives data sent via HTTP POST, it is added to $_POST superglobal array.

When the visitor submits a form via HTTP POST, the PHP interpreter receives the request for the page and adds the form data (sent in the HTTP headers) to the $_POST superglobal array.

The code in the PHP file can access the values in the $_POST superglobal array in the same way that it would access values from any associative array. If the form control is a text input, there will always be a value for it.

```php
<?php
    $name = $_POST['user_name'];
    $email = $_POST['user_email'];
    $message = $_POST['user_message'];
    
    var_dump($name);
    var_dump($email);
    var_dump($message);
?>
```
### How to check if a form has been submitted

The $_SERVER superglobal array has a key called **REQUEST_METHOD**, which stores the HTTP method used to request that page.

#### Check for POST example
```php
<?php
    if ($_SERVER['REQUEST_METHOD'] == 'POST') {
        $term = $_POST['term'];
        echo 'You searched for ' . htmlspecialchars($term);
    } else { ?>
        <form action="check-for-http-post.php" method="POST">
        Search for: <input type="search" name="term">
        <input type="submit" value="search">
        </form>
<?php } ?>
```

#### Check for GET example
```php
<?php
    $submitted = $_GET['sent'] ?? '';
    if ($submitted === 'search') { 
        $term = $_GET['term'] ?? '';
        echo 'You searched for ' . htmlspecialchars($term);
    } else { ?>
        <form action="check-for-http-get.php" method="GET">
        Search for: <input type="search" name="term">
        <input type="submit" name="sent" value="search">
        </form>
<?php } ?>
```