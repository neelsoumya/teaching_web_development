# Introduction to PHP

PHP (Hypertext Preprocessor) is a popular server-side scripting language designed for web development but also used as a general-purpose programming language. 

It is especially suited for creating dynamic web pages and applications.

## Resources

- [Video Tutorial on PHP by Dr. Chuck Severance](https://youtu.be/srw_5veGPyg?si=HKIJlFpNOWJyDfgb)

- [Video Tutorial on PHP by Dr. Chuck Severance](https://youtu.be/CwwF801i5_4?si=xg2zXI4IzsRBIrqG)

- [Online PHP compiler](https://www.w3schools.com/php/phptryit.asp?filename=tryphp_compiler)


## Features

- Inspired by C and Perl
- Loosely typed language
- Supports Object-Oriented Programming (OOP)
- Extends HTML capabilities

## Philosophy of PHP
- PHP is designed to be easy to learn and use
- It emphasizes simplicity and speed
- Not an exercise in building the most elegant or consistent language possible
- Errors fail silently by default to avoid disrupting the user experience
- If you make mistakes, you are responsible for finding and fixing them


## Key Features of PHP

- **Server-Side Scripting:** PHP code is executed on the server, generating HTML that is sent to the client's browser.
- **Embedded in HTML:** PHP can be embedded directly within HTML code, making it easy to create dynamic web content.
- **Database Integration:** PHP has built-in support for various databases, including MySQL, PostgreSQL, and SQLite, allowing for dynamic data-driven applications.
- **Cross-Platform:** PHP runs on various platforms, including Windows, Linux, and macOS, making it versatile for different server environments.
- **Open Source:** PHP is free to use and has a large community that contributes to its development and provides support.


## Example PHP Code

- Interleaved HTML and PHP code:

```php
<h1> Hello from HTML </h1>

<?php
// This is a simple PHP script that outputs "Hello, World!"
echo "Hello, World!";
?>

<p> This is more HTML content. </p>

```

- The output of the above code will be:

```
Hello from HTML
Hello, World!
This is more HTML content.
```

- 🚀 _Concept_: Output from PHP is substituted into the HTML at the location of the PHP code.

- 🚀 _Concept_: It runs on the server, and the client only sees the resulting HTML.



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


## 📝 Examples

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

## Implicit type conversions

- ⚠️ PHP performs implicit type conversions when necessary.
- For example, when a string is used in a numeric context, PHP will attempt to convert it to a number.

```php
<?php
$number = "10"; // string
$sum = $number + 5; // PHP converts $number to an integer
echo $sum; // Outputs: 15
?>
```

- ⚠️ Be cautious with implicit conversions, as they can lead to unexpected results.


## Operators

- PHP supports various operators for arithmetic, comparison, logical operations, and more.
- Examples of operators:

```php
<?php
$a = 10;
$b = 5; 
$sum = $a + $b; // Addition
$difference = $a - $b; // Subtraction
$product = $a * $b; // Multiplication
$quotient = $a / $b; // Division
$isEqual = ($a == $b); // Comparison
$isGreater = ($a > $b); // Comparison
$andCondition = ($a > 5 && $b < 10); // Logical AND
$orCondition = ($a < 5 || $b < 10); // Logical OR
?>
```
- == will perform type conversion if the types of the operands are different.
- === will not perform type conversion and will check both value and type.
- 🚀 _NOTE_: = is the assignment operator.


## Increment and Decrement Operators
- PHP provides increment (`++`) and decrement (`--`) operators to increase or decrease the value of a variable by one.
```php
<?php
$x = 5;
$x++; // Increment: $x is now 6
$y = 10;
$y--; // Decrement: $y is now 9
?>
```
- These operators can be used in both prefix and postfix forms.
```php
<?php
$a = 3;
$b = ++$a; // Prefix: $a is incremented to 4, then assigned to $b
$c = $a++; // Postfix: $c is assigned the value 4, then $a is incremented to 5
?>
```
- The prefix form increments or decrements the variable before its value is used in an expression, while the postfix form uses the variable's current value before incrementing or decrementing it.


<!--🧩 Fun Activity      -->
<!--🚀 Fun Activity      -->

## 🎮 Fun Activity        <!-- interactive / playful -->



- What values will be printed by the following code?

```php
<?php
$x = 12;
$y = 15 + $x++;
echo "x is $x and y is $y";
$z = 20 + ++$x;
echo "x is $x and y is $y and z is $z";
?>
```

<!--
- The output will be:
```x is 13 and y is 27x is 14 and y is 27 and z is 34
```
-->

## String concatenation

- The . (dot) operator is used for string concatenation

- 🤔 _Remember_: The + (plus) operator will try to aggeressively type convert and add

- Example code below:

```php
<?php

$a = "Hello " . "World";
echo $a . "\n";

?>
```

## Side effect assignment

- ⚠️ _NOTE_ This is not a good practice

- Use them sparingly but I show them for the sake of completeness

- Try the following code in the [online PHP compiler](https://www.w3schools.com/php/phptryit.asp?filename=tryphp_compiler)


```php
<?php

$x = 10;
$x += 2;
echo $x;

?>
```

## Type casting

- PHP does aggressive type casting

- Floating point

```php
<?php

$x = 56;
$y = 12;
echo $x / $y;

?>
```

### Activities: 🎮

- What will be the output of the following code?

```php
<?php

$z = "100" + 36.25 + TRUE;
echo $z;

?>
```

- Explicit type casting

- 🛠️ What will be the output of this code?

```php

<?php

echo "100" + (string) 10;

?>
```

- 💡 What will be the output of this code?

```php
<?php

echo "100" . string(10)

?>
```

- And this?


```php
<?php

echo (int) 9.9 - 1.9;

?>
```