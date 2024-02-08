# PHP Basics

## PHP Short Echo Tag
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
PHP has a built-in function called isset() which accepts a variable name, a key of an array, or a property of an object as an argument. It returns true 
