# Exams and Quizzes

This section outlines the structure and content of exams and quizzes that will be administered throughout the course to assess students' understanding and mastery of the material covered.

---

# Quiz: PHP & Web Development Fundamentals

### Questions

**1. Outputting Data**
Which of the following PHP statements is valid for outputting the text "Hello World" to the browser?

* A) `echo "Hello World";`
* B) `print "Hello World";`
* C) `<?= "Hello World" ?>`
* D) All of the above

**2. Variable Syntax**
Which of the following is a **valid** PHP variable name?

* A) `var $user_name;`
* B) `$user-name`
* C) `$user_name`
* D) `@userName`

**3. Comparison Operators**
What is the result of the following comparison: `(5 === "5")`?

* A) `TRUE`
* B) `FALSE`
* C) `NULL`
* D) An error occurs

**4. Form Handling**
When a standard HTML form is submitted with `<form method="post">`, which PHP superglobal array is populated with the form data?

* A) `$_GET`
* B) `$_REQUEST`
* C) `$_POST`
* D) `$_SERVER`

**5. File Inclusion**
What is the primary difference between `include 'file.php'` and `require 'file.php'`?

* A) `include` stops the script execution if the file is missing; `require` does not.
* B) `require` stops the script execution (Fatal Error) if the file is missing; `include` only emits a warning and continues.
* C) `require` is used for HTML files; `include` is used for PHP files.
* D) There is no difference; they are aliases of the same function.

**6. Arrays**
Given the array `$colors = ["red" => "#FF0000", "green" => "#00FF00"];`, how do you access the hex code for green?

* A) `$colors[1]`
* B) `$colors["green"]`
* C) `$colors->green`
* D) `array_values($colors, "green")`

**7. Session Management**
Where are PHP Session variables (`$_SESSION`) typically stored by default?

* A) On the user's computer (in a cookie).
* B) In the URL query string.
* C) On the server.
* D) Inside the HTML hidden fields.

**8. Security (SQL Injection)**
Which of the following is the **most effective** way to prevent SQL Injection attacks when querying a database?

* A) Using `strip_tags()` on user input.
* B) Using Prepared Statements (with PDO or MySQLi).
* C) Removing all spaces from the user input.
* D) Trusting that the user will only enter valid data.

**9. HTTP Protocol**
Which HTTP status code represents a "Page Not Found" error?

* A) 200
* B) 301
* C) 404
* D) 500

**10. JSON Handling**
You receive a JSON string from an API and need to convert it into a PHP array or object. Which function do you use?

* A) `json_encode()`
* B) `json_parse()`
* C) `json_decode()`
* D) `array_to_json()`

---

### Answer Key

| Question | Correct Answer | Explanation |
| --- | --- | --- |
| **1** | **D** | All listed methods are valid. `echo` and `print` are language constructs; `<?=` is the short echo tag. |
| **2** | **C** | PHP variables must start with `$` followed by a letter or underscore. Hyphens (`-`) are not allowed. |
| **3** | **B** | `===` checks both value and type. The integer `5` is not the same type as the string `"5"`. |
| **4** | **C** | `$_POST` is used specifically for form data sent via the HTTP POST method. |
| **5** | **B** | `require` is stricter; it stops the script if the file is missing, whereas `include` allows the script to keep running. |
| **6** | **B** | In an associative array, values are accessed using their defined keys (strings). |
| **7** | **C** | Session data is stored on the server side. The client only holds a session ID (usually in a cookie). |
| **8** | **B** | Prepared statements separate code from data, preventing malicious SQL injection. |
| **9** | **C** | 404 is the standard HTTP response code for "Not Found". |
| **10** | **C** | `json_decode()` converts a JSON string into a PHP variable. `json_encode()` does the reverse. |

