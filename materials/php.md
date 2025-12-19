# Introduction to PHP

PHP (Hypertext Preprocessor) is a popular server-side scripting language designed for web development but also used as a general-purpose programming language. 

It is especially suited for creating dynamic web pages and applications.

## Key Features of PHP

- **Server-Side Scripting:** PHP code is executed on the server, generating HTML that is sent to the client's browser.
- **Embedded in HTML:** PHP can be embedded directly within HTML code, making it easy to create dynamic web content.
- **Database Integration:** PHP has built-in support for various databases, including MySQL, PostgreSQL, and SQLite, allowing for dynamic data-driven applications.
- **Cross-Platform:** PHP runs on various platforms, including Windows, Linux, and macOS, making it versatile for different server environments.
- **Open Source:** PHP is free to use and has a large community that contributes to its development and provides support.

## Video Tutorial

[Video Tutorial on PHP by Dr. Chuck Severance](https://youtu.be/CwwF801i5_4?si=xg2zXI4IzsRBIrqG)


## Getting Started with PHP

- [Installation Instructions](installation.md)

- [Run on server](https://www.w3schools.com/php/phptryit.asp?filename=tryphp_version)

- Start MAMP on your machine.

_ Click on "Start" to start the Apache server.

- Navigate to `http://localhost:8888` or `http://localhost:8888/MAMP/?language=English` in your web browser to verify that the server is running.

## Configuring PHP 

- Edit the file `php.ini` to configure PHP settings.

- On my Mac OS X, the file is located at:

  ```
  /Applications/MAMP/bin/php/php8.3.28/conf/php.ini
  ```

- The contents of `php.ini` look like this:

  ```
  ; PHP's initialization file, generally called php.ini, is responsible for
  ; configuring many of the aspects of PHP's behavior.
  ;
  ; This file is divided into sections, each section having directives that
  ; configure various aspects of PHP's behavior. Each directive is explained
  ; via comments in this file.
  ;
  ; For more information about setting up PHP, please refer to the
  ; documentation at https://www.php.net/manual/en/configuration.file.php
  ```

- Start writing PHP code in your web server's document root directory (e.g., `htdocs` for MAMP).

- On my Mac OS X, the document root directory is located at:

  ```
  /Applications/MAMP/htdocs
  ```

- In this directory, create a new folder named `my_php_site`.

- In this folder, create a file with a `.php` extension (e.g., `index.php`) to start writing your PHP code.

- Open your favorite code editor (e.g., VS Code, vi, Sublime Text, or any text editor) to write PHP code.

- Write the PHP code in the `.php` file you created.

```php
<?php
// Your PHP code goes here
echo "Hello World!";
?>
```

- Navigate to `http://localhost:8888/my_php_site/index.php` in your web browser to see the output of your PHP code.



## PHP Script

- A PHP script is typically enclosed within `<?php` and `?>` tags.

- A PHP file usually has a `.php` extension.

- A PHP script can generate HTML content dynamically.


## Syntax Basics

- [PHP Syntax](https://www.w3schools.com/php/php_syntax.asp)

- [PHP Variables](https://www.w3schools.com/php/php_variables.asp)

- PHP is loosely typed, meaning you do not need to declare variable types explicitly.

- Static typing can be found in C++ or Java, where you must declare the type of a variable before using it.

- Dynamic typing means that the type is determined at runtime based on the value assigned to the variable.

- For example:

```php
<?php
$age = 25; // $age is an integer
$name = "Alice"; // $name is a string
$price = 19.99; // $price is a float
?>
```

- [PHP Data Types](https://www.w3schools.com/php/php_datatypes.asp)

- [PHP Operators](https://www.w3schools.com/php/php_operators.asp)

## Examples

- [PHP Examples](https://www.w3schools.com/php/php_examples.asp)

- Example code snippets:

```php
<?php
// Example 1: Variables and Output
$name = "John";
echo "Hello, " . $name . "!"; // Outputs: Hello, John!
?>
```

```php
<?php
// Example 2: Conditional Statements
$age = 20;
if ($age >= 18) {
    echo "You are an adult.";
} else {
    echo "You are a minor.";
}
?>
```


```php
<?php
// Example 3: Looping
for ($i = 1; $i <= 5; $i++) {
    echo "Number: " . $i . "<br>";
}
?>
```

```php
<?php
// Example 4: Functions
function greet($name) {
    return "Hello, " . $name . "!";
} 

echo greet("Alice"); // Outputs: Hello, Alice!
?>
```


```php
<?php
// Example 5: Arrays
$fruits = array("Apple", "Banana", "Cherry");
foreach ($fruits as $fruit) {
    echo $fruit . "<br>";
}
?>
```

