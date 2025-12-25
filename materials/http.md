# Resources on HTTP

# HTTP — a practical chapter for PHP & web programming

This chapter explains the Hypertext Transfer Protocol (HTTP) at a level suitable for undergraduate web programming students who are using PHP. It mixes conceptual material with hands-on PHP examples and practical debugging tips.

[Coursera HTTP](https://www.coursera.org/learn/web-applications-php/lecture/CQrbf/hypertext-transfer-protocol-http): A video lecture on HTTP from the associated Coursera course.

---

## 1. What is HTTP?

HTTP is an application-level protocol for exchanging messages between clients (usually browsers or API clients) and servers (web servers + application code). It is **request → response**: a client sends a request and the server returns a response.

Key ideas:

* **Stateless**: by default each request is independent. State is layered on top (cookies, sessions, tokens).
* **Textual** protocol (requests/responses are readable ASCII/UTF-8 lines) with structured headers and optional body.
* Runs over TCP (usually). When using `https://` it is HTTP over TLS.

---

## 2. Anatomy of an HTTP request and response

### Raw HTTP request (example)

```
GET /index.php?q=php-http HTTP/1.1
Host: example.com
User-Agent: curl/8.0
Accept: text/html
Cookie: session=abcd1234
```

### Raw HTTP response (example)

```
HTTP/1.1 200 OK
Date: Tue, 16 Dec 2025 12:00:00 GMT
Content-Type: text/html; charset=utf-8
Content-Length: 142

<!doctype html>
<html><body><h1>Hello</h1></body></html>
```

Sections:

* **Start line**: request line (`METHOD PATH PROTOCOL`) or status line (`PROTOCOL STATUS REASON`).
* **Headers**: key: value pairs (metadata).
* **Blank line**
* **Body**: optional payload (HTML, JSON, images, file data).

---

## 3. Important HTTP methods and semantics

* **GET** — retrieve a resource. Safe & cacheable. Should be idempotent.
* **HEAD** — same as GET but no body; used to fetch headers.
* **POST** — submit data to server (create/modify). Not idempotent by default.
* **PUT** — replace a resource. Idempotent.
* **PATCH** — partial update.
* **DELETE** — delete a resource. Idempotent.
* **OPTIONS** — ask server about supported methods & CORS preflight.

**Idempotent**: same request repeated yields same result (e.g., PUT, GET).

---

## 4. Common response status codes (quick reference)

* **1xx**: informational
* **2xx**: success

  * `200 OK`, `201 Created`, `204 No Content`
* **3xx**: redirection

  * `301 Moved Permanently`, `302 Found`, `304 Not Modified`
* **4xx**: client error

  * `400 Bad Request`, `401 Unauthorized`, `403 Forbidden`, `404 Not Found`, `422 Unprocessable Entity`
* **5xx**: server error

  * `500 Internal Server Error`, `502 Bad Gateway`, `503 Service Unavailable`

Use the correct code to make APIs predictable for clients.

---

## 5. Headers you meet often (request & response)

* `Host` — required for virtual hosting.
* `Content-Type` — MIME type of the body, e.g. `application/json`, `text/html`, `multipart/form-data`.
* `Accept` — what the client can accept.
* `Authorization` — credentials, e.g. `Bearer <token>`.
* `Cookie` / `Set-Cookie` — session cookies.
* `Cache-Control`, `ETag`, `Last-Modified` — caching.
* `Location` — for redirects.
* `Access-Control-Allow-Origin`, `Access-Control-Allow-Methods` — CORS control.

---

## 6. Request & response lifecycle (high level)

1. Client resolves domain → DNS → IP.
2. TCP (and TLS if HTTPS) handshake.
3. Client sends HTTP request.
4. Server (webserver or reverse proxy) routes request to application (PHP-FPM, CGI, built-in server).
5. Application processes request and returns headers + body.
6. Connection closed or re-used (keep-alive).
7. Client processes response (render, cache, call next API).

---


### URL (Uniform Resource Locator) components

- **Scheme:** Indicates the protocol to be used (e.g., `http`, `https`).
- **Host:** The domain name or IP address of the server (e.g., `www.example.com`).
- **Port:** Optional; specifies the port number on the server (e.g., `:80` for HTTP, `:443` for HTTPS).

Here is a diagram illustrating the components of a URL:

```
   +--------+    +------------------+    +------+    +------------------+
   | Scheme | -> |      Host        | -> | Port | -> |      Path        |
   +--------+    +------------------+    +------+    +------------------+
       |               |                    |                |
     http://       www.example.com         :80          /index.php?q=test
```



### Port

In web programming, a **port** is a **number that identifies which service or application on a computer should receive network traffic**.


Think of a computer as a **large building** with **many doors**:

* The **IP address** is the building’s street address
* The **port number** is the **specific door**
* Each door leads to a **different service**

So when data arrives over the internet, the port tells the computer *which program should handle it*.


> A **port** is a logical endpoint used by the operating system to route incoming and outgoing network data to the correct application.

- Why ports are needed

A single machine can run many network services at the same time:

* A web server
* An email server
* A database server

Ports allow all of these to coexist on **one IP address** without confusion.

- Common examples in web programming

|     Port | Purpose                                  |
| -------: | ---------------------------------------- |
|   **80** | HTTP (standard web pages)                |
|  **443** | HTTPS (secure web pages)                 |
| **3000** | Common for development servers (Node.js) |
| **3306** | MySQL database                           |
| **5432** | PostgreSQL database                      |

- In a URL

Ports appear **after the hostname**, separated by a colon:

```
http://localhost:3000
https://example.com:443
```

* `localhost` → the computer
* `3000` → which service on that computer

If no port is specified, the browser **assumes the default**:

* HTTP → port 80
* HTTPS → port 443

- _One-sentence takeaway_

> A **port** tells your computer *which program* should receive the network request, just like a door number tells you which room to enter.






## 7. Testing & debugging tools

* Browser DevTools (Network tab)
* `curl` / `httpie`
* Postman / Insomnia
* Server logs (Nginx/Apache), PHP error log
* `php -S localhost:8000` — simple PHP web server for development

Examples:

```bash
# simple GET
curl -i http://localhost:8000/index.php?q=test

# POST JSON
curl -i -X POST http://localhost:8000/api.php \
  -H "Content-Type: application/json" \
  -d '{"name":"Alice"}'
```

---


## 8. PHP server basics & handling requests

### Start built-in server (dev)

```bash
# from your project directory
php -S localhost:8000
```

### Reading GET and POST

```php
// GET parameters
$q = $_GET['q'] ?? null;

// POST form-encoded
$name = $_POST['name'] ?? null;

// Raw body (for JSON APIs)
$raw = file_get_contents('php://input');
$data = json_decode($raw, true);
```

### Sending headers and status codes

```php
// set a status code
http_response_code(201);

// set custom header
header('Content-Type: application/json');

// send JSON response
echo json_encode(['id' => 123, 'name' => 'Alice']);
```

### Redirect

```php
header('Location: /login.php');
http_response_code(302);
exit;
```

### Set cookie

```php
setcookie('session', $sessionId, [
  'expires' => time() + 3600,
  'path' => '/',
  'httponly' => true,
  'secure' => true,       // only over HTTPS
  'samesite' => 'Lax',
]);
```

---

## 9. Building a tiny REST endpoint in PHP

`api.php`

```php
<?php
// simple router
$method = $_SERVER['REQUEST_METHOD'];
$path = parse_url($_SERVER['REQUEST_URI'], PHP_URL_PATH);

if ($path === '/api/notes' && $method === 'GET') {
    header('Content-Type: application/json');
    echo json_encode(['notes' => [['id'=>1,'text'=>'Intro to HTTP']]]);
    exit;
}

if ($path === '/api/notes' && $method === 'POST') {
    $raw = file_get_contents('php://input');
    $body = json_decode($raw, true);
    if (!isset($body['text'])) {
        http_response_code(400);
        echo json_encode(['error' => 'text required']);
        exit;
    }
    // pretend to create note...
    http_response_code(201);
    header('Content-Type: application/json');
    echo json_encode(['id' => 2, 'text' => $body['text']]);
    exit;
}

http_response_code(404);
echo "Not found";
```

Test with `curl`:

```bash
curl -i http://localhost:8000/api/notes
curl -i -X POST http://localhost:8000/api/notes \
  -H "Content-Type: application/json" \
  -d '{"text":"Learn HTTP"}'
```

---

## 10. Content negotiation & APIs

Clients declare `Accept`; servers choose response format. For simple APIs, support JSON (`application/json`) only and return `415 Unsupported Media Type` if Content-Type is wrong.

Example content-type check:

```php
if ($_SERVER['CONTENT_TYPE'] !== 'application/json') {
    http_response_code(415);
    echo json_encode(['error' => 'Expected application/json']);
    exit;
}
```

---

## 11. Caching basics

* `Cache-Control` (no-cache, max-age, public/private)
* `ETag` and `If-None-Match` — server can return `304 Not Modified` when content unchanged.
* Use caching for static assets and expensive computations.

Example:

```php
header('Cache-Control: public, max-age=3600');
```

---

## 12. Security basics for HTTP

### Always use HTTPS in production

* TLS prevents eavesdropping and tampering.
* Redirect HTTP → HTTPS and use HSTS (`Strict-Transport-Security`).

### Cookies

* `Secure`, `HttpOnly`, and `SameSite` attributes.
* Prefer session identifiers not predictable; regenerate on privilege change.

### CORS (Cross-Origin Resource Sharing)

* Browser security model blocks cross-origin requests unless server allows them.
* Simple allow-all example (only for trusted APIs; don't use in production broadly):

```php
header('Access-Control-Allow-Origin: https://your-frontend.example');
header('Access-Control-Allow-Methods: GET, POST, OPTIONS');
header('Access-Control-Allow-Headers: Content-Type, Authorization');
```

Handle `OPTIONS` preflight by returning allowed headers and methods with `204 No Content`.

### CSRF (Cross-Site Request Forgery)

* POST actions should be protected by CSRF tokens or use SameSite cookies + proper authentication.
* For APIs with `Authorization: Bearer <token>`, CSRF is less relevant since tokens aren't sent automatically by browsers.

### Input validation & escaping

* Validate server-side. Never trust client data.
* Use prepared statements for DBs (PDO with bound params).
* Escape output in HTML contexts (avoid XSS).

---

## 13. File uploads (multipart/form-data)

HTML form:

```html
<form method="post" enctype="multipart/form-data" action="/upload.php">
  <input type="file" name="avatar">
  <button>Upload</button>
</form>
```

PHP handling:

```php
if (!empty($_FILES['avatar']) && $_FILES['avatar']['error'] === UPLOAD_ERR_OK) {
    $tmp = $_FILES['avatar']['tmp_name'];
    $name = basename($_FILES['avatar']['name']);
    $dest = __DIR__ . '/uploads/' . $name;
    move_uploaded_file($tmp, $dest);
    echo "Saved";
} else {
    echo "Upload failed";
}
```

Security: validate MIME type and file extensions, store outside web root or with randomized names, limit size.

---

## 14. Advanced topics (brief)

* **HTTP/2**: multiplexed streams, header compression (improves performance).
* **HTTP/3 (QUIC)**: UDP-based transport; still behind server and client support.
* **Streaming**: Server-Sent Events, chunked transfer encoding.
* **WebSockets**: separate protocol for persistent bi-directional connections (upgrade handshake begins over HTTP).

---

## 15. Common mistakes & pitfalls

* Returning `200` on errors (use appropriate 4xx/5xx).
* Relying on `$_POST` for JSON payloads (need `php://input`).
* Not setting `Content-Type` on responses.
* Allowing `Access-Control-Allow-Origin: *` for authenticated endpoints.
* Storing uploaded files with original filenames (risk of overwrites & path traversal).

---

## 16. Exercises (quick, with suggested answers)

### Exercise 1 — GET vs POST

Q: Why should form submissions that change server state use POST instead of GET?
A: GET is intended for safe retrieval and can be cached/bookmarked/appears in logs/URL. POST signals non-idempotent change and hides payload from URL.

### Exercise 2 — Implement JSON API

Task: Write a PHP endpoint `/api/echo` that accepts JSON `{"message":"..."}` and returns `{"echo":"..."}` with status `200`.
Suggested answer (skeleton):

```php
$raw = file_get_contents('php://input');
$data = json_decode($raw, true);
if (!isset($data['message'])) {
  http_response_code(400);
  echo json_encode(['error'=>'message required']);
  exit;
}
header('Content-Type: application/json');
echo json_encode(['echo' => $data['message']]);
```

### Exercise 3 — CORS preflight

Q: What response should the server send to an `OPTIONS` preflight request?
A: Return `204 No Content` (or `200`) with `Access-Control-Allow-Origin`, `Access-Control-Allow-Methods`, and `Access-Control-Allow-Headers` including whatever the client requested.

---

## 17. Further reading & resources

* MDN Web Docs (HTTP concepts) — great reference for semantics and headers.
* RFC 7230–7235 (HTTP/1.1) — authoritative spec (read selectively).
* PHP manual: functions: `header()`, `setcookie()`, `session_*`, file upload docs.
* Browser DevTools network tab — practice inspecting headers and bodies.
* `curl` manual — useful for scripting tests.



[Next: GET and POST methods](materials/get.md)