# Exams and Quizzes

This section outlines the structure and content of exams and quizzes that will be administered throughout the course to assess students' understanding and mastery of the material covered.

---

# Assessment

Portfolio: Create and test a cross platform website with interactive elements using a scripting language. 




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




## More assignments 


### **Assignment 1: HTML Basics - Personal Profile Page**

**Objective:** Create a personal profile page using semantic HTML elements.

**Requirements:**
- Use proper HTML5 structure (DOCTYPE, html, head, body)
- Include a header with your name and a navigation menu
- Create sections for: About Me, Education, Hobbies, and Contact
- Use various HTML elements: headings, paragraphs, lists (ordered and unordered), images, and links
- Include at least one table showing your weekly schedule
- Add a footer with copyright information

**Answer:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>John Doe - Profile</title>
</head>
<body>
    <header>
        <h1>John Doe</h1>
        <nav>
            <ul>
                <li><a href="#about">About</a></li>
                <li><a href="#education">Education</a></li>
                <li><a href="#hobbies">Hobbies</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="about">
            <h2>About Me</h2>
            <img src="profile.jpg" alt="Profile picture" width="200">
            <p>Hello! I'm a first-year computer science student passionate about web development.</p>
        </section>

        <section id="education">
            <h2>Education</h2>
            <ul>
                <li><strong>University:</strong> ABC University</li>
                <li><strong>Degree:</strong> Bachelor of Computer Science</li>
                <li><strong>Year:</strong> First Year</li>
            </ul>
        </section>

        <section id="hobbies">
            <h2>Hobbies</h2>
            <ol>
                <li>Coding</li>
                <li>Reading tech blogs</li>
                <li>Playing video games</li>
            </ol>
        </section>

        <section id="contact">
            <h2>Contact Information</h2>
            <table border="1">
                <tr>
                    <th>Method</th>
                    <th>Details</th>
                </tr>
                <tr>
                    <td>Email</td>
                    <td>john.doe@example.com</td>
                </tr>
                <tr>
                    <td>Phone</td>
                    <td>+1234567890</td>
                </tr>
            </table>
        </section>
    </main>

    <footer>
        <p>&copy; 2024 John Doe. All rights reserved.</p>
    </footer>
</body>
</html>
```

---

### **Assignment 2: CSS Styling - Enhanced Profile Page**

**Objective:** Style the profile page created in Assignment 1 using CSS.

**Requirements:**
- Create an external CSS file and link it to your HTML
- Style the header with a background color and centered text
- Create a horizontal navigation menu with hover effects
- Use different fonts and colors for headings and paragraphs
- Add padding and margins to sections
- Style the table with alternating row colors
- Make the page responsive with a max-width container

**Answer:**

HTML (add to head section):
```html
<link rel="stylesheet" href="style.css">
```

CSS (style.css):
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    color: #333;
}

header {
    background-color: #2c3e50;
    color: white;
    padding: 20px 0;
    text-align: center;
}

header h1 {
    margin-bottom: 15px;
}

nav ul {
    list-style: none;
    display: flex;
    justify-content: center;
    gap: 30px;
}

nav a {
    color: white;
    text-decoration: none;
    padding: 10px 15px;
    transition: background-color 0.3s;
}

nav a:hover {
    background-color: #34495e;
    border-radius: 5px;
}

main {
    max-width: 900px;
    margin: 0 auto;
    padding: 20px;
}

section {
    margin: 30px 0;
    padding: 20px;
    background-color: #f4f4f4;
    border-radius: 8px;
}

section h2 {
    color: #2c3e50;
    margin-bottom: 15px;
    border-bottom: 2px solid #3498db;
    padding-bottom: 10px;
}

img {
    border-radius: 50%;
    display: block;
    margin: 15px 0;
}

table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 15px;
}

table th {
    background-color: #3498db;
    color: white;
    padding: 12px;
}

table td {
    padding: 10px;
}

table tr:nth-child(even) {
    background-color: #ecf0f1;
}

footer {
    background-color: #2c3e50;
    color: white;
    text-align: center;
    padding: 15px 0;
    margin-top: 30px;
}
```

---

### **Assignment 3: HTML Forms and CSS - Student Registration Form**

**Objective:** Create a student registration form with proper validation attributes and styling.

**Requirements:**
- Create a form with fields: name, email, password, date of birth, gender (radio buttons), courses (checkboxes), country (dropdown), and comments (textarea)
- Use appropriate input types and validation attributes
- Style the form to be user-friendly
- Add a submit and reset button

**Answer:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Registration</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            padding: 20px;
        }

        .form-container {
            max-width: 600px;
            margin: 0 auto;
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }

        h1 {
            text-align: center;
            color: #2c3e50;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
            color: #555;
        }

        input[type="text"],
        input[type="email"],
        input[type="password"],
        input[type="date"],
        select,
        textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 14px;
        }

        input[type="radio"],
        input[type="checkbox"] {
            margin-right: 5px;
        }

        .radio-group,
        .checkbox-group {
            margin-top: 8px;
        }

        .radio-group label,
        .checkbox-group label {
            display: inline;
            font-weight: normal;
            margin-right: 15px;
        }

        textarea {
            resize: vertical;
            min-height: 100px;
        }

        .button-group {
            text-align: center;
            margin-top: 25px;
        }

        button {
            padding: 12px 30px;
            margin: 0 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }

        button[type="submit"] {
            background-color: #3498db;
            color: white;
        }

        button[type="submit"]:hover {
            background-color: #2980b9;
        }

        button[type="reset"] {
            background-color: #e74c3c;
            color: white;
        }

        button[type="reset"]:hover {
            background-color: #c0392b;
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h1>Student Registration Form</h1>
        <form action="submit.php" method="POST">
            <div class="form-group">
                <label for="fullname">Full Name:</label>
                <input type="text" id="fullname" name="fullname" required>
            </div>

            <div class="form-group">
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>
            </div>

            <div class="form-group">
                <label for="password">Password:</label>
                <input type="password" id="password" name="password" minlength="6" required>
            </div>

            <div class="form-group">
                <label for="dob">Date of Birth:</label>
                <input type="date" id="dob" name="dob" required>
            </div>

            <div class="form-group">
                <label>Gender:</label>
                <div class="radio-group">
                    <input type="radio" id="male" name="gender" value="male" required>
                    <label for="male">Male</label>
                    <input type="radio" id="female" name="gender" value="female">
                    <label for="female">Female</label>
                    <input type="radio" id="other" name="gender" value="other">
                    <label for="other">Other</label>
                </div>
            </div>

            <div class="form-group">
                <label>Select Courses:</label>
                <div class="checkbox-group">
                    <input type="checkbox" id="html" name="courses[]" value="HTML">
                    <label for="html">HTML</label><br>
                    <input type="checkbox" id="css" name="courses[]" value="CSS">
                    <label for="css">CSS</label><br>
                    <input type="checkbox" id="php" name="courses[]" value="PHP">
                    <label for="php">PHP</label><br>
                    <input type="checkbox" id="aspnet" name="courses[]" value="ASP.NET">
                    <label for="aspnet">ASP.NET</label>
                </div>
            </div>

            <div class="form-group">
                <label for="country">Country:</label>
                <select id="country" name="country" required>
                    <option value="">Select Country</option>
                    <option value="usa">United States</option>
                    <option value="uk">United Kingdom</option>
                    <option value="canada">Canada</option>
                    <option value="india">India</option>
                    <option value="australia">Australia</option>
                </select>
            </div>

            <div class="form-group">
                <label for="comments">Comments:</label>
                <textarea id="comments" name="comments"></textarea>
            </div>

            <div class="button-group">
                <button type="submit">Submit</button>
                <button type="reset">Reset</button>
            </div>
        </form>
    </div>
</body>
</html>
```

---

### **Assignment 4: PHP Basics - Form Processing**

**Objective:** Process the registration form data using PHP and display it.

**Requirements:**
- Create a PHP file to receive form data
- Validate that required fields are filled
- Sanitize user input
- Display the submitted data in a formatted manner
- Show appropriate error messages for invalid data

**Answer:**

**submit.php:**
```php
<?php
// Check if form was submitted
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    
    // Initialize error array
    $errors = array();
    
    // Sanitize and validate input
    $fullname = isset($_POST['fullname']) ? htmlspecialchars(trim($_POST['fullname'])) : '';
    $email = isset($_POST['email']) ? filter_var(trim($_POST['email']), FILTER_SANITIZE_EMAIL) : '';
    $password = isset($_POST['password']) ? $_POST['password'] : '';
    $dob = isset($_POST['dob']) ? htmlspecialchars($_POST['dob']) : '';
    $gender = isset($_POST['gender']) ? htmlspecialchars($_POST['gender']) : '';
    $courses = isset($_POST['courses']) ? $_POST['courses'] : array();
    $country = isset($_POST['country']) ? htmlspecialchars($_POST['country']) : '';
    $comments = isset($_POST['comments']) ? htmlspecialchars(trim($_POST['comments'])) : '';
    
    // Validation
    if (empty($fullname)) {
        $errors[] = "Full name is required";
    }
    
    if (empty($email) || !filter_var($email, FILTER_VALIDATE_EMAIL)) {
        $errors[] = "Valid email is required";
    }
    
    if (empty($password) || strlen($password) < 6) {
        $errors[] = "Password must be at least 6 characters";
    }
    
    if (empty($dob)) {
        $errors[] = "Date of birth is required";
    }
    
    if (empty($gender)) {
        $errors[] = "Gender is required";
    }
    
    if (empty($country)) {
        $errors[] = "Country is required";
    }
    
    ?>
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Registration Result</title>
        <style>
            body {
                font-family: Arial, sans-serif;
                background-color: #f0f0f0;
                padding: 20px;
            }
            .container {
                max-width: 700px;
                margin: 0 auto;
                background-color: white;
                padding: 30px;
                border-radius: 10px;
                box-shadow: 0 0 10px rgba(0,0,0,0.1);
            }
            h1 {
                color: #2c3e50;
                text-align: center;
            }
            .success {
                background-color: #d4edda;
                border: 1px solid #c3e6cb;
                color: #155724;
                padding: 15px;
                border-radius: 5px;
                margin-bottom: 20px;
            }
            .error {
                background-color: #f8d7da;
                border: 1px solid #f5c6cb;
                color: #721c24;
                padding: 15px;
                border-radius: 5px;
                margin-bottom: 20px;
            }
            .info-table {
                width: 100%;
                border-collapse: collapse;
                margin-top: 20px;
            }
            .info-table th {
                background-color: #3498db;
                color: white;
                padding: 12px;
                text-align: left;
            }
            .info-table td {
                padding: 10px;
                border-bottom: 1px solid #ddd;
            }
            .info-table tr:nth-child(even) {
                background-color: #f9f9f9;
            }
            .back-link {
                display: block;
                text-align: center;
                margin-top: 20px;
                color: #3498db;
                text-decoration: none;
            }
            .back-link:hover {
                text-decoration: underline;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <?php if (!empty($errors)): ?>
                <div class="error">
                    <h2>Errors:</h2>
                    <ul>
                        <?php foreach ($errors as $error): ?>
                            <li><?php echo $error; ?></li>
                        <?php endforeach; ?>
                    </ul>
                </div>
                <a href="javascript:history.back()" class="back-link">Go Back</a>
            <?php else: ?>
                <div class="success">
                    <h2>Registration Successful!</h2>
                    <p>Thank you for registering. Here are your details:</p>
                </div>
                
                <table class="info-table">
                    <tr>
                        <th>Field</th>
                        <th>Value</th>
                    </tr>
                    <tr>
                        <td><strong>Full Name:</strong></td>
                        <td><?php echo $fullname; ?></td>
                    </tr>
                    <tr>
                        <td><strong>Email:</strong></td>
                        <td><?php echo $email; ?></td>
                    </tr>
                    <tr>
                        <td><strong>Date of Birth:</strong></td>
                        <td><?php echo $dob; ?></td>
                    </tr>
                    <tr>
                        <td><strong>Gender:</strong></td>
                        <td><?php echo ucfirst($gender); ?></td>
                    </tr>
                    <tr>
                        <td><strong>Courses:</strong></td>
                        <td>
                            <?php 
                            if (!empty($courses)) {
                                echo implode(", ", array_map('htmlspecialchars', $courses));
                            } else {
                                echo "None selected";
                            }
                            ?>
                        </td>
                    </tr>
                    <tr>
                        <td><strong>Country:</strong></td>
                        <td><?php echo ucfirst($country); ?></td>
                    </tr>
                    <tr>
                        <td><strong>Comments:</strong></td>
                        <td><?php echo !empty($comments) ? $comments : "No comments"; ?></td>
                    </tr>
                </table>
                
                <a href="registration.html" class="back-link">Register Another Student</a>
            <?php endif; ?>
        </div>
    </body>
    </html>
    <?php
} else {
    header("Location: registration.html");
    exit();
}
?>
```

---

### **Assignment 5: ASP.NET - Simple Calculator Web Application**

**Objective:** Create a basic calculator using ASP.NET Web Forms.

**Requirements:**
- Create a web form with two textboxes for numbers
- Add radio buttons or dropdown for operation selection (Add, Subtract, Multiply, Divide)
- Include a Calculate button
- Display the result on the same page
- Handle division by zero error

**Answer:**

**Calculator.aspx:**
```aspx
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Calculator.aspx.cs" Inherits="WebApp.Calculator" %>

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            padding: 20px;
        }
        .calculator-container {
            max-width: 500px;
            margin: 0 auto;
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        h1 {
            text-align: center;
            color: #2c3e50;
        }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
            color: #555;
        }
        .textbox {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
        }
        .radio-group {
            margin: 10px 0;
        }
        .radio-group label {
            display: inline;
            font-weight: normal;
            margin-right: 15px;
        }
        .button {
            width: 100%;
            padding: 12px;
            background-color: #3498db;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
        }
        .button:hover {
            background-color: #2980b9;
        }
        .result {
            margin-top: 20px;
            padding: 15px;
            background-color: #d4edda;
            border: 1px solid #c3e6cb;
            border-radius: 5px;
            text-align: center;
            font-size: 18px;
            font-weight: bold;
        }
        .error {
            background-color: #f8d7da;
            border: 1px solid #f5c6cb;
            color: #721c24;
        }
    </style>
</head>
<body>
    <form id="form1" runat="server">
        <div class="calculator-container">
            <h1>Simple Calculator</h1>
            
            <div class="form-group">
                <label for="txtNumber1">First Number:</label>
                <asp:TextBox ID="txtNumber1" runat="server" CssClass="textbox" TextMode="Number"></asp:TextBox>
                <asp:RequiredFieldValidator ID="rfvNumber1" runat="server" 
                    ControlToValidate="txtNumber1" 
                    ErrorMessage="First number is required" 
                    ForeColor="Red">
                </asp:RequiredFieldValidator>
            </div>
            
            <div class="form-group">
                <label for="txtNumber2">Second Number:</label>
                <asp:TextBox ID="txtNumber2" runat="server" CssClass="textbox" TextMode="Number"></asp:TextBox>
                <asp:RequiredFieldValidator ID="rfvNumber2" runat="server" 
                    ControlToValidate="txtNumber2" 
                    ErrorMessage="Second number is required" 
                    ForeColor="Red">
                </asp:RequiredFieldValidator>
            </div>
            
            <div class="form-group">
                <label>Select Operation:</label>
                <div class="radio-group">
                    <asp:RadioButtonList ID="rblOperation" runat="server" RepeatDirection="Horizontal">
                        <asp:ListItem Text="Add" Value="add" Selected="True"></asp:ListItem>
                        <asp:ListItem Text="Subtract" Value="subtract"></asp:ListItem>
                        <asp:ListItem Text="Multiply" Value="multiply"></asp:ListItem>
                        <asp:ListItem Text="Divide" Value="divide"></asp:ListItem>
                    </asp:RadioButtonList>
                </div>
            </div>
            
            <div class="form-group">
                <asp:Button ID="btnCalculate" runat="server" Text="Calculate" 
                    CssClass="button" OnClick="btnCalculate_Click" />
            </div>
            
            <asp:Panel ID="pnlResult" runat="server" Visible="false" CssClass="result">
                <asp:Label ID="lblResult" runat="server"></asp:Label>
            </asp:Panel>
        </div>
    </form>
</body>
</html>
```

**Calculator.aspx.cs:**
```csharp
using System;
using System.Web.UI;

namespace WebApp
{
    public partial class Calculator : Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            // Page load logic if needed
        }

        protected void btnCalculate_Click(object sender, EventArgs e)
        {
            try
            {
                // Parse the input numbers
                double num1 = Convert.ToDouble(txtNumber1.Text);
                double num2 = Convert.ToDouble(txtNumber2.Text);
                double result = 0;
                string operation = rblOperation.SelectedValue;
                string operationSymbol = "";

                // Perform calculation based on selected operation
                switch (operation)
                {
                    case "add":
                        result = num1 + num2;
                        operationSymbol = "+";
                        break;
                    case "subtract":
                        result = num1 - num2;
                        operationSymbol = "-";
                        break;
                    case "multiply":
                        result = num1 * num2;
                        operationSymbol = "×";
                        break;
                    case "divide":
                        if (num2 == 0)
                        {
                            lblResult.Text = "Error: Cannot divide by zero!";
                            pnlResult.CssClass = "result error";
                            pnlResult.Visible = true;
                            return;
                        }
                        result = num1 / num2;
                        operationSymbol = "÷";
                        break;
                }

                // Display the result
                lblResult.Text = $"Result: {num1} {operationSymbol} {num2} = {result:F2}";
                pnlResult.CssClass = "result";
                pnlResult.Visible = true;
            }
            catch (Exception ex)
            {
                lblResult.Text = "Error: Please enter valid numbers";
                pnlResult.CssClass = "result error";
                pnlResult.Visible = true;
            }
        }
    }
}
```

## CSS and github.io assignments



# 🚀 Part 1: In-Class Activity (30–45 minutes)

### *“Deploy Your First Stylised Website”*

### Learning goals

By the end of the activity, students will:

* Publish a webpage using **GitHub Pages**
* Link an external **CSS stylesheet**
* Use basic CSS to control **layout, colour, fonts, and spacing**
* Experience the joy of seeing something “live” on the internet

---

## Activity Brief (Student-Facing)

> You will create and publish a **single-page website** on `github.io`, styled using CSS.
> Choose a theme:
>
> * **XKCD-style comic page**
> * **Star Wars opening crawl**
> * **Retro terminal / hacker page**
> * **Your own fun theme**

Your page must be **online** by the end of the session.

---

## Step-by-Step Instructions

### 1️⃣ Setup (10 minutes)

1. Create a GitHub account (if needed).

2. Create a new repository called:

   ```
   username.github.io
   ```

3. Add two files:

   * `index.html`
   * `style.css`

4. Enable **GitHub Pages**
   → Settings → Pages → Deploy from main branch

---

### 2️⃣ Starter HTML (provided)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My Fun Webpage</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <header>
    <h1>Welcome to My Page</h1>
    <p>A long time ago, in a browser far, far away…</p>
  </header>

  <main>
    <section>
      <h2>About</h2>
      <p>This page is styled entirely with CSS.</p>
    </section>
  </main>

</body>
</html>
```

---

### 3️⃣ CSS Challenge (20 minutes)

Students must:

* Change background colour or gradient
* Choose a font (system font or Google Fonts)
* Style headings differently from body text
* Center or animate at least one element

#### Example: Star Wars-Style Crawl

```css
body {
  background: black;
  color: yellow;
  font-family: 'Arial', sans-serif;
  overflow: hidden;
}

main {
  width: 60%;
  margin: auto;
  font-size: 1.5em;
  text-align: justify;
  animation: crawl 20s linear infinite;
}

@keyframes crawl {
  from { transform: translateY(100%); }
  to { transform: translateY(-200%); }
}
```

#### Example: XKCD-Style

```css
body {
  font-family: "Comic Sans MS", cursive;
  background: white;
  color: black;
}

h1 {
  border-bottom: 2px solid black;
}

section {
  max-width: 600px;
  margin: auto;
}
```

---

### 4️⃣ Show & Tell (5–10 minutes)

* Students paste their live URLs in chat
* Quick gallery walk
* Vote for:

  * *Funniest*
  * *Most Stylish*
  * *Most Ridiculous*

🏆 Small prizes or bragging rights recommended.

---

# 🌌 Part 2: Larger Assignment (Take-Home, 1–2 weeks)

### *“Theme Website: Style as Storytelling”*

---

## Assignment Brief

Create a **themed website** hosted on GitHub Pages that uses **CSS to express a narrative or aesthetic**.

You may work **individually or in pairs**.

### Suggested Themes

* XKCD-inspired explainer page
* Star Wars opening crawl (with multiple sections)
* “Old Internet” (GeoCities vibes)
* Sci-fi terminal interface
* Minimalist academic homepage
* Fake startup landing page

---

## Technical Requirements (Graded)

Your site **must include**:

### HTML

* At least **3 sections** (`header`, `main`, `footer` or similar)
* Semantic HTML (`section`, `nav`, `article`)
* Clean indentation

### CSS

* External stylesheet
* At least:

  * 3 selectors
  * 1 class selector
  * 1 ID selector
* Use of:

  * Fonts
  * Colours
  * Spacing (margin/padding)
* One of:

  * Animation
  * Hover effect
  * Responsive layout (media query)

### Deployment

* Hosted on `username.github.io`
* Public repository
* Working URL submitted

---

## Marking Rubric (Example)

| Criterion                 | Marks   |
| ------------------------- | ------- |
| CSS correctness & clarity | 30      |
| Visual creativity & theme | 25      |
| HTML structure            | 20      |
| GitHub Pages deployment   | 15      |
| Code readability          | 10      |
| **Total**                 | **100** |

---

## Optional Stretch Goals 🌟

* Use Flexbox or Grid
* Dark/light mode toggle
* Embedded image or SVG
* Accessibility (contrast, readable fonts)




## Responsible AI visualization assignment

- Assignment brief — Visualization tools for responsible AI decision-making

- Responsible-AI Visualization Prototype

---

## Overview & motivation

AI systems increasingly provide recommendations that affect people’s lives (medical triage, loan decisions, hiring suggestions, content moderation, etc.). A good visualization can help stakeholders (end users, domain experts, auditors, policy makers) understand AI outputs, assess uncertainty, identify risks, and make responsible decisions. In this assignment you will design, build, and evaluate a small web-based visualization tool that supports responsible decision-making when interacting with an AI model.

---

## Learning objectives

By the end of this project you should be able to:

* Apply HCI and information-visualization principles to represent model outputs, uncertainty, and provenance.
* Build an interactive web prototype that connects a simple AI or simulated model to visual components.
* Conduct lightweight user-centred research (persona mapping, simple user testing) and iterate on design.
* Critically reflect on ethical issues (bias, transparency, privacy, misuse) and accessibility in visualization design.
* Communicate design decisions, technical approach, and evaluation results in a concise report and demo.

---

## Project brief / task

Design and implement a browser-based interactive visualization that helps a chosen stakeholder group make responsible choices based on AI output.

You must:

1. **Define a use case & stakeholder.** (E.g., clinicians reviewing risk predictions, loan officers assessing credit recommendations, moderators reviewing content-safety scores, or a public user interpreting news summarisation confidence.)
2. **Select or simulate an AI model.** You may either (a) use a simple pre-trained model or API (e.g., sentiment classifier, risk score generator), (b) load a small dataset and implement a basic classifier/regression in JavaScript/Python and expose outputs, or (c) simulate model outputs (label + confidence + provenance + counterfactuals). The model complexity is less important than how you present and interrogate its outputs.
3. **Design visualization(s).** Show model output, uncertainty, explanation (feature importance, example cases, counterfactuals), provenance or data lineage where possible, and decision options for the stakeholder. Prioritize clarity, critiqueability, and support for responsible actions.
4. **Prototype interactions.** Allow users to: inspect an individual case, compare alternative model outputs/parameters, explore uncertainty, and record/justify a decision.
5. **Perform a short user evaluation.** Run formative testing with at least 3–5 participants (classmates are fine), collect qualitative feedback, and iterate once. Report key findings and changes made.
6. **Write a short report and README.** Explain design goals, technologies used, evaluation summary, ethical considerations, how to run the prototype, and next steps.

---

## Deliverables

1. **GitHub repository** (public or private link + invitation) containing:

   * All source code and assets.
   * `README.md` with clear run/setup instructions and a short project description.
   * Short deployment (GitHub Pages, Vercel, Netlify, or instructions for local run).
2. **Interactive prototype** accessible via link or runnable locally.
3. **Design report** (maximum 1500 words) including:

   * Use case & stakeholder description.
   * Design rationale and visualization choices.
   * Model description or explanation of simulated data.
   * User testing method, participant summary, findings, and iterations.
   * Ethical, privacy, and accessibility considerations.
4. **Demo video** (3–5 minutes) or live demo in class: walk through the tool and highlight how it supports responsible decision-making.
5. **Optional:** UI mockups, personas, low-fidelity sketches, or source of datasets.


---

## Technical & design guidance

* **Visualization principles:** show raw evidence where helpful, use small-multiple comparisons, make uncertainty salient (intervals, ensembles, calibration plots), and provide explainability aids (feature importance, counterfactuals, example cases).
* **Accessibility:** ensure readable text, keyboard navigation, and consider colorblind-friendly encodings.
* **Data & model:** If you use real datasets, strip or anonymize any personal/sensitive data. If using external APIs, ensure rate limits and privacy are handled.
* **Ethics:** identify potential misuse (e.g., over-reliance on the model), and document limitations and safeguards in the report.

---

## User testing suggestions (quick)

* Give a short scenario + task (e.g., “Decide whether to accept or escalate this case using the tool”).
* Use think-aloud or brief structured questions.
* Capture 10–15 minutes of feedback per user.
* Synthesize into 3–5 actionable changes and implement at least one.

---

## Report structure (recommended)

1. Title & team members
2. One-paragraph problem statement & stakeholder.
3. Design goals & key requirements.
4. Technical approach / model summary.
5. Screenshots / flow diagrams.
6. User testing: tasks, participants, findings, iterations.
7. Ethics & accessibility reflection.
8. How to run / demo link.
9. Future work.

---

## Submission instructions

* Push code to GitHub and share the repository link.
* Upload the design report (PDF or Markdown) to the repo root and/or submit via the course submission portal.
* Include the demo video link (YouTube unlisted or repo `video/` file).
* Tag your release or create a PR labelled `assignment-resp-ai-viz`.
* Deadline: please follow the course deadline (if unspecified, aim for four weeks after assignment). Late submissions may incur penalties as per course policy.

---

## Extensions & stretch goals (optional)

* Add role-based views (different visuals for auditors vs. end users).
* Implement interactive counterfactual generation (let users tweak inputs to see outcome changes).
* Integrate provenance metadata showing training data examples or model versioning.
* Implement lightweight fairness metrics and visualizations (e.g., group comparisons).

---


---

## Hints & quick checklist

* Start with a clear scenario and a paper prototype before coding.
* Keep scope small: a single, well-polished interaction beats many half-built features.
* Prioritize explainability and uncertainty over fancy visuals.
* Test early with real people and iterate.

---

---
