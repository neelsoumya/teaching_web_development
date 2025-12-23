
# Installing PHP on macOS

### Best Option

- [MAMP](https://www.mamp.info/en/downloads/) is a popular choice for macOS, bundling Apache, MySQL, and PHP. However, for simplicity and ease of use, we recommend using **Homebrew** to install PHP directly.

- Start MAMP and navigate to `http://localhost:8888` to verify the installation.

- [MAMP localhost](http://localhost:8888/MAMP/?language=English) shows the MAMP welcome page.


# Installing web development tools

- [Chris Pederick's Web Developer Extension](https://chrispederick.com/work/web-developer/): A browser extension that adds various web development tools.





# Other options


* If you want the **fastest, lowest-friction** route for beginners, use an all-in-one local AMP stack (XAMPP on Windows/Linux, MAMP on macOS/Windows, or Laragon on Windows). These install Apache, PHP and MariaDB/MySQL in a few clicks and are easy for labs. ([apachefriends.org][1])

[XAMPP](https://sourceforge.net/projects/xampp/)

* If you want a **more modern, reproducible** setup that matches server environments and is useful later in the degree, use Docker (PHP-FPM + Nginx + MariaDB). Docker makes the environment identical across student laptops. ([Docker Documentation][2])
* Use **Composer** for any dependency management / autoloading so students learn modern PHP practices early. ([getcomposer.org][3])
* Teach debugging with **Xdebug** + VS Code (breakpoints, step-through) — it’s much more effective than print debugging. ([xdebug.org][4])
* Teach with a current PHP stable (PHP 8.x at time of writing). Check the PHP site periodically for the exact recommended version. ([PHP][5])

---

# Option A — Beginner (recommended for first lab week)

**Tools:** XAMPP (Windows/Linux/macOS) or MAMP (macOS/Windows) or Laragon (Windows)
**Good for:** quick start, no Docker knowledge required.

Steps (students):

1. Download & install XAMPP / MAMP / Laragon. Start Apache & MySQL from the control panel. ([apachefriends.org][1])
2. Put project files in the web folder:

   * XAMPP: `C:\xampp\htdocs\yourproject` (Windows) or `/opt/lampp/htdocs/` (Linux)
   * MAMP: `/Applications/MAMP/htdocs/` (macOS)
   * Laragon: `C:\laragon\www\yourproject`
3. Open `http://localhost/yourproject` in the browser.
4. Use phpMyAdmin (bundled) to create a database for labs.

*When to use:* first 2–3 weeks (HTML, simple PHP scripts, forms, GET/POST, simple DB CRUD).

---

# Option B — Modern / reproducible (recommended for course staff and advanced labs)

**Tools:** Docker + docker-compose (students will need Docker Desktop or Docker Engine)
**Good for:** reproducible environment, matching production, group projects.

Here’s a minimal `docker-compose.yml` you can give students to run a PHP + Nginx + MariaDB stack:

```yaml
version: "3.8"
services:
  web:
    image: php:8.2-fpm
    container_name: php-fpm
    volumes:
      - ./www:/var/www/html
      - ./php.ini:/usr/local/etc/php/conf.d/custom.ini
    depends_on:
      - db

  nginx:
    image: nginx:stable
    ports:
      - "8080:80"
    volumes:
      - ./www:/var/www/html
      - ./nginx/default.conf:/etc/nginx/conf.d/default.conf
    depends_on:
      - web

  db:
    image: mariadb:10.11
    environment:
      MYSQL_ROOT_PASSWORD: rootpw
      MYSQL_DATABASE: class_db
    volumes:
      - db_data:/var/lib/mysql

  phpmyadmin:
    image: phpmyadmin/phpmyadmin
    environment:
      PMA_HOST: db
    ports:
      - "8081:80"
    depends_on:
      - db

volumes:
  db_data:
```

(Students place their PHP files under `./www` and visit `http://localhost:8080`.) For a more complete Docker teaching guide see Docker’s PHP development docs. ([Docker Documentation][2])

---

# Editor & tooling (what I recommend for teaching)

* **Visual Studio Code** — lightweight, cross-platform, great extensions and a good student experience. (Teach the basics of the editor in the first session.) ([Visual Studio Code][6])
* VS Code extensions:

  * **Intelephense** (IntelliSense for PHP)
  * **PHP Debug** (connects to Xdebug)
  * **PHP CS Fixer / phpcs** (optional: coding style)
  * **Live Server** (for HTML/CSS static previews)
    (Show students how to install extensions from the Extensions view.)
* **Composer** — teach `composer init`, `composer require`, and PSR-4 autoloading early. ([getcomposer.org][3])
* **Xdebug** — set up for breakpoints and step debugging in VS Code. Explain common config values (remote_enable, client_host, client_port). ([xdebug.org][4])

---

# Minimal file examples (copy-paste into student projects)

`www/index.php`

```php
<?php
// index.php - simple safe DB example using PDO
require_once __DIR__.'/config.php';

try {
    $pdo = new PDO($DB_DSN, $DB_USER, $DB_PASS, [
        PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
        PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
    ]);
} catch (Exception $e) {
    echo "DB connection error.";
    exit;
}

// Simple prepared statement (prevents SQL injection)
$stmt = $pdo->prepare('SELECT id, name, email FROM users LIMIT 10');
$stmt->execute();
$users = $stmt->fetchAll();
?>
<!doctype html>
<html>
<head><meta charset="utf-8"><title>Class demo</title></head>
<body>
  <h1>Users</h1>
  <ul>
    <?php foreach ($users as $u): ?>
      <li><?= htmlspecialchars($u['name']) ?> — <?= htmlspecialchars($u['email']) ?></li>
    <?php endforeach; ?>
  </ul>
</body>
</html>
```

`www/config.php`

```php
<?php
// config.php - simple credentials for local development
$DB_DSN  = 'mysql:host=db;dbname=class_db;charset=utf8mb4'; // for Docker example
$DB_USER = 'root';
$DB_PASS = 'rootpw';
```

(If using XAMPP/MAMP put `host=localhost` and DB creds accordingly.)

---

# Security & best practices to teach early (one slide each)

* Never interpolate raw input into SQL — use **prepared statements** (PDO).
* Escape output with `htmlspecialchars()` when printing HTML.
* Use `password_hash()` / `password_verify()` for passwords.
* Validate + sanitize form input on the server (don’t rely on the browser).
* Explain the basics of CSRF and introduce CSRF tokens for forms later.

---

# Short 6-week mini-syllabus & lab ideas (for 1st year)

Week 1 — HTML & CSS basics, browser devtools, file structure (MDN + small static page). ([MDN Web Docs][7])
Week 2 — Intro PHP: echo, variables, control flow, embedding PHP in HTML (php.net simple tutorial). ([PHP][8])
Week 3 — Forms, GET/POST, basic validation, and XSS prevention.
Week 4 — Databases: MySQL/MariaDB basics (use phpMyAdmin), CRUD with PDO prepared statements.
Week 5 — Sessions, login/logout, `password_hash`, simple auth flow.
Week 6 — Small group project: a simple “student directory” web app (create/read/update/delete and search).

Each lab should include a short spec, starter repo (or zip) and an automated test or checklist (staff can review with a rubric).

---

# Assignments / assessment ideas

* **Practical quiz:** small tasks in a live environment (create a form, save to DB, display results).
* **Code review:** students submit a PR and peers + staff review security & style.
* **Mini project:** 2–3 week group project with a short report and demo.

---

# Teaching materials & student resources (good, up-to-date sources)

* **PHP Manual (official)** — comprehensive reference and tutorials. ([PHP][9])
* **MDN Learn (HTML/CSS)** — excellent beginner tutorials and explanations. ([MDN Web Docs][7])
* **freeCodeCamp HTML/CSS tutorials** — approachable tutorials & videos for beginners. ([FreeCodeCamp][10])
* **Laracasts** (PHP for Beginners) — short video series, very clear for newcomers. ([Laracasts][11])
* **Composer docs** — how to install and use Composer. ([getcomposer.org][3])
* **Xdebug docs** — installation & usage. ([xdebug.org][4])
* **Docker official guide for PHP** — good for introducing containerized dev. ([Docker Documentation][2])

(If you want a printable reading list / slide deck I can produce one now — say “Make me a 1-page student handout” and I’ll generate it.)

---

# Practical checklist for first session (copy to a lab sheet)

1. Install XAMPP / MAMP / Laragon **or** Docker Desktop. (Give both options.) ([apachefriends.org][1])
2. Install VS Code and the recommended extensions. ([Visual Studio Code][6])
3. Start Apache/PHP + MySQL (or `docker-compose up`) and open `http://localhost`.
4. Clone starter repo or unpack starter zip into `www` folder.
5. Run through “Hello PHP” page -> explain `<?php ?>` tags and server output.

---

# Want files / starter repos?

I can:

* produce a ready-to-use `docker-compose.yml`, `nginx/default.conf`, and starter `www/` folder (zippable), **or**
* make a 1-page lab handout or slide deck for Week 1 (PDF or Markdown), or
* create a set of 6 short assignment specs with rubrics.

Tell me which of those you want and I’ll generate the files and code in this chat right now (no waiting).

* a complete working `docker-compose.yml` + `nginx/default.conf` + zip-ready file tree, **or**
* create a one-page student handout (compact step-by-step first lab).


[1]: https://www.apachefriends.org/download.html?utm_source=chatgpt.com "Download XAMPP"
[2]: https://docs.docker.com/guides/php/develop/?utm_source=chatgpt.com "Use containers for PHP development"
[3]: https://getcomposer.org/doc/00-intro.md?utm_source=chatgpt.com "Introduction"
[4]: https://xdebug.org/docs/install?utm_source=chatgpt.com "Xdebug: Documentation » Installation"
[5]: https://www.php.net/?utm_source=chatgpt.com "PHP"
[6]: https://code.visualstudio.com/docs/languages/php?utm_source=chatgpt.com "PHP in Visual Studio Code"
[7]: https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content?utm_source=chatgpt.com "Structuring content with HTML - Learn web development | MDN"
[8]: https://www.php.net/manual/en/tutorial.php?utm_source=chatgpt.com "A simple tutorial - Manual"
[9]: https://www.php.net/manual/en/index.php?utm_source=chatgpt.com "PHP: PHP Manual - Manual"
[10]: https://www.freecodecamp.org/news/html-crash-course/?utm_source=chatgpt.com "HTML for Beginners"
[11]: https://laracasts.com/series/php-for-beginners-2023-edition?utm_source=chatgpt.com "PHP For Beginners"
