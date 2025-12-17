# Introduction to PHP

PHP (Hypertext Preprocessor) is a popular server-side scripting language designed for web development but also used as a general-purpose programming language. 

It is especially suited for creating dynamic web pages and applications.

## Key Features of PHP

- **Server-Side Scripting:** PHP code is executed on the server, generating HTML that is sent to the client's browser.
- **Embedded in HTML:** PHP can be embedded directly within HTML code, making it easy to create dynamic web content.
- **Database Integration:** PHP has built-in support for various databases, including MySQL, PostgreSQL, and SQLite, allowing for dynamic data-driven applications.
- **Cross-Platform:** PHP runs on various platforms, including Windows, Linux, and macOS, making it versatile for different server environments.
- **Open Source:** PHP is free to use and has a large community that contributes to its development and provides support.

## Getting Started with PHP

- [Installation Instructions](installation.md)

- [Run on server](https://www.w3schools.com/php/phptryit.asp?filename=tryphp_version)


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



## Your First PHP Script

- A PHP script is typically enclosed within `<?php` and `?>` tags.

- A PHP file usually has a `.php` extension.

- A PHP script can generate HTML content dynamically.


- To create your first PHP script, follow these steps:

  1. Ensure you have a web server with PHP installed (e.g., MAMP, XAMPP, or a local server setup).
  
  2. Create a new file named `index.php` in your web server's document root directory (e.g., `htdocs` for MAMP).

  3. Add the following code to `index.php`:

  ```php
  <?php
  echo "Hello, World!";
  ?>
  ```

  4. Open your web browser and navigate to `http://localhost/index.php` (or the appropriate URL based on your server setup).

  5. You should see "Hello, World!" displayed in your browser.

## Syntax Basics

- [PHP Syntax](https://www.w3schools.com/php/php_syntax.asp)