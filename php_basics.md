# PHP Util 
Here is a list of some helpful PHP features:

## PHP Short Echo Tag
PHP echo is a command to output text or variables to the web browser.
The short echo tag <?= is a short-hand to the more verbose <?php echo. 
```php
    <?php
        //regular echo inside php tag
        echo "Some value goes here";
    ?>    
        //short echo tag
    <?= 'Some value goes here' ?>
```

## PHP including & requiring files

### include
The include keyword tells the PHP interpreter to get another file from the server and treat it as if the contents of that file had been written where the include statement is written.

It is followed by the path to the file written in the quotes. (You sometimes see the filename and quotes in parentheses, but they are not needed.) The include file should use the **.php** file extension.

```php
    <?php
        include 'someFile.php';
    ?>
```
### require
```php
    <?php
        require 'someFile.php';
    ?>
```

### difference between include & require
- The include and require keywords both add the code from the file they are referring to
- The only difference is how the interpreter behaves if the included file cannot be found or read:
    - **include**: the interpreter generates an error, but keeps trying to process the rest of the page.
    - **require**: the interpreter generates an error, then stops trying to process the rest of the page.

Additional Resources:
- https://clouddevs.com/php/include-and-require/

## isset() vs. empty()

### isset()
returns true if the specified variable is set and not null, or if the specified key exists in an array and is not null. It's commonly used to check if a variable or array key exists before accessing it to avoid errors and warnings in PHP scripts

### empty()
is another built-in function in PHP that checks whether a variable is empty. It returns true if the variable is considered empty. A variable is considered empty if it does not exist, or if its value equals false, 0, an empty string, an empty array, NULL, or a variable declared with no value.


**This example illustrates the differences between isset() and empty()**

```php
<?php
// Define variables
$var1 = ""; // Empty string
$var2 = null; // Null value
$var3 = 0; // Zero
$var4; // Undefined variable

// Check using isset()
echo "Using isset():<br>";
echo "var1 is " . (isset($var1) ? "set" : "not set") . "<br>"; // Output: var1 is set
echo "var2 is " . (isset($var2) ? "set" : "not set") . "<br>"; // Output: var2 is not set
echo "var3 is " . (isset($var3) ? "set" : "not set") . "<br>"; // Output: var3 is set
echo "var4 is " . (isset($var4) ? "set" : "not set") . "<br>"; // Otput: var4 is not set

// Check using empty()
echo "<br>Using empty():<br>";
echo "var1 is " . (empty($var1) ? "empty" : "not empty") . "<br>"; // Output: var1 is empty
echo "var2 is " . (empty($var2) ? "empty" : "not empty") . "<br>"; // Output: var2 is empty
echo "var3 is " . (empty($var3) ? "empty" : "not empty") . "<br>"; // Output: var3 is empty
echo "var4 is " . (empty($var4) ? "empty" : "not empty") . "<br>"; // Output: var4 is empty
?>
```
