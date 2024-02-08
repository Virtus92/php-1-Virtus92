## Sending Data with GET or POST

**HTTP** specifies two ways that browsers can send data to the server<br>
**HTTP GET** puts the data in the query string at the end of the URL<br>
**HTTP POST** adds the data to the HTTP headers.<br>

## GET

When sending data to a web page via **HTTP GET**, the browser puts the data in a query string and adds it to the end of the URL for the page. A question mark separates the URL for the page from the query string.

A query string can hold several name/value pairs. An equals sign separates each name from its value. To send more than one name/value pair, separate each one with an ampersand **&**.

```html
<a href='someUrl?id=3&name=Susi&age=23'>
```

## POST

When sending data via HTTP POST, the browser adds extra name/value pairs to the HTTP request headers. The browser can send multiple name/value pairs to the server with each request.
The headers are not shown in the main browser window, but you can see them in the developer tool that come with most browsers.

## How data is send from links and forms

HTML uses links and forms to send additional data to the server at the same time as requesting a page.

A link can use a query string to send extra data to the server. The data in the query string usually tells the server to get specific information and display that data on the page that it returns.

### Sending data from links

A link can use a query string to send extra data to the server. The data in the query string usually tells the server to get specific information and display that data on the page that it returns.

Typically, HTTP GET is used when a browser wants to get information from the server, and that information would be the same for every visitor to the site. For example, when they:

- Click links to display specific information
- Enter a search term into a form

### Sending data from forms

Forms have inputs that allow users to enter text or numbers, select one of a list of options, or check a box. The form data can be added to the query string or sent in the HTTP headers.

```html
<form action="/some-form-handling-page" method="post">
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

Typically, HTTP POST is used when a user is sending (or posting) information to the server that either identifies them or is used to update the data stored about them on the server. For example, when they

- Sign into their personal account
- Purchase a product
- Subscribe to a service
- Agree to terms & conditions