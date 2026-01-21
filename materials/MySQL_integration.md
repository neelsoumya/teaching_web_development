# SQL integration with PHP

## Overview

Integrating SQL databases with PHP is essential for building dynamic web applications that can store, retrieve, and manipulate data. This section covers the basics of connecting to a MySQL database using PHP, executing SQL queries, and handling the results.

## Connecting to a MySQL Database

To connect to a MySQL database using PHP, you can use the `mysqli` extension or PDO (PHP Data Objects). Here’s an example using `mysqli`:

```php
$servername = "localhost";
$username = "username";
$password = "password";
$dbname = "database_name";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);
// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
echo "Connected successfully";
```

## Executing SQL Queries
Once connected, you can execute SQL queries using the `query` method. Here’s an example of selecting data from a table:

```php
$sql = "SELECT id, name, email FROM Users";
$result = $conn->query($sql);
if ($result->num_rows > 0) {
    // Output data of each row
    while($row = $result->fetch_assoc()) {
        echo "id: " . $row["id"]. " - Name: " . $row["name"]. " - Email: " . $row["email"]. "<br>";
    }
} else {
    echo "0 results";
}
```

## Inserting Data into the Database
You can also insert data into the database using an `INSERT` SQL statement:
```php
$sql = "INSERT INTO Users (name, email) VALUES ('John Doe', 'john@example.com')";
if ($conn->query($sql) === TRUE) {
    echo "New record created successfully";
} else {
    echo "Error: " . $sql . "<br>" . $conn->error;
}
```

## Closing the Connection
After completing your database operations, it’s important to close the connection:
```php
$conn->close();
```

## Best Practices
- Always sanitize user inputs to prevent SQL injection attacks. Use prepared statements with parameterized queries.
- Example of a SQL injection attack is here:
  ```php
  $stmt = $conn->prepare("SELECT id, name, email FROM Users WHERE email = ?");
  $stmt->bind_param("s", $email);
  $stmt->execute();
  $result = $stmt->get_result();
  ```
  - Example of preventing SQL injection using prepared statements:
  ```php
  $stmt = $conn->prepare("INSERT INTO Users (name, email) VALUES (?, ?)");
  $stmt->bind_param("ss", $name, $email);
  $stmt->execute();
  ```
  
- Use error handling to manage database connection issues and query failures.
- Handle database errors gracefully and log them for debugging.

## References

- [PHP MySQL w3schools](https://www.w3schools.com/php/php_mysql_intro.asp): A comprehensive guide on using MySQL with PHP.


- [Next: HCI fundamentals](HCI.md)