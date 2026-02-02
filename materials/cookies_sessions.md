# Cookies and Sessions

- Cookies and sessions are two fundamental concepts in web development that help manage user state and data across multiple requests. Understanding how they work and when to use each is crucial for building effective web applications.

- [Video by Dr. Severance on cookies and sessions](https://youtu.be/WvGPeF-qHHQ?si=D6B-yKENhi8u39j7)
- [Video by Dr. Severance on sessions](https://youtu.be/DbHZ5THxt4s?si=26kJmJ4tfmYo-uJZ)


## What are cookies?

- Cookies are temporary storage on client browser

- Server uses it store information

- Request/response is stateless. So you need a mechanism to save state.

- Little breadcrumnbs/cookies to save state

## Code

```html

<?php
// Note - cannot have any output before setcookie
if (! isset($_COOKIE['var_cookie']) ){
    setcookie('var_cookie', '23', time() + 4000);
}

print_r($_COOKIE);
?>

```

## Sessions

- [Video by Dr. Severance on sessions](https://youtu.be/DbHZ5THxt4s?si=26kJmJ4tfmYo-uJZ)

- Make state persist across request response cycles

- Shopping cart or login information stored in sessions

- A large random number that is hard to guess. Stored as key value pairs

- If you find out the number you can get access

- `session_start()`

- can now store value in `$_SESSION` variable

- `session_destroy()`

## Session code





- [Next: HCI fundamentals](HCI.md)
