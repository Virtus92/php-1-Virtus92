# Basic Login 
This example will show you a simple Login/ Logout Feature.
## session.php

```php
<?php
session_start(); // Start/renew session
$logged_in = $_SESSION['logged_in'] ?? false; // Is user logged in?

$email = 'ivy@eg.link'; // Email address to login
$password  = 'password'; // Password to login

function login() // Remember user passed login
{
    session_regenerate_id(true); // Update session id
    $_SESSION['logged_in'] = true; // Set logged_in key to true
}

function logout() // Terminate the session
{
    $_SESSION = []; // Clear contents of array
    $params = session_get_cookie_params();// Get session cookie parameters
    setcookie('PHPSESSID', '', time() - 3600, $params['path'], $params['domain'],
        $params['secure'], $params['httponly']); // Delete session cookie

    session_destroy();  // Delete session file
}

function require_login($logged_in) // Check if user logged in
{
    if ($logged_in == false) { // If not logged in
        header('Location: login.php'); // Send to login page
        exit; // Stop rest of page running
    }
}
```
## account.php
```php
<?php 
include 'sessions.php';
require_login($logged_in); // Redirect user if not logged in
?>

<?php include 'includes/header-member.php'; // Include new header file 
?>
```
## header-member.php
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Chapter 9 Examples</title>
    <link href="css/styles.css" rel="stylesheet">
  </head>
  <body>
    <div class="page">
      <header>
        <a href="index.php"><img src="img/logo.png" alt="Mountain Art Supplies" height="90"></a>
      </header>
      <nav>
        <a href="home.php">Home</a>
        <a href="products.php">Products</a>
        <a href="account.php">My Account</a>
        <?= $logged_in ? '<a href="logout.php">Log Out</a>' : '<a href="login.php">Log In</a>'; ?>
      </nav>
      <section>
```
## login.php
```php
<?php
include 'sessions.php';

if ($logged_in) { // If already logged in
    header('Location: account.php'); // Redirect to account page
    exit; // Stop further code running
}    

if($_SERVER['REQUEST_METHOD'] == 'POST') { // If form submitted
    $user_email    = $_POST['email']; // Email user sent
    $user_password = $_POST['password']; // Password user sent

    if ($user_email == $email and $user_password == $password) { // If details correct
        login(); // Call login function
        header('Location: account.php'); // Redirect to account page
        exit; // Stop further code running
    }
}
?>
//form
<?php include 'includes/header-member.php'; ?>
<h1>Login</h1>
<form method="POST" action="login.php">
  Email: <input type="email" name="email"><br>
  Password: <input type="password" name="password"><br>
  <input type="submit" value="Log In">
</form>
<?php include 'footer.php'; ?>
```
## logout.php
```php
<?php
include 'includes/sessions.php';
logout();  // Call logout() to terminate session
header('Location: home.php');  
```
