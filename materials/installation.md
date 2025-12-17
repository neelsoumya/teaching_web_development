# Installation Guide

This guide will help you set up a local development environment for PHP using XAMPP, MAMP, or Docker. Follow the steps below to get started.

Below is a **clear, step-by-step guide to installing PHP** for undergraduate web programming. It covers the three most common platforms and ends with a quick sanity check and common pitfalls.

---

# Installing PHP (for Web Programming)

This guide installs **PHP 8.x**, suitable for modern web development and coursework.

---

## 1. Check if PHP is already installed

Open a terminal (Command Prompt / PowerShell on Windows) and run:

```bash
php -v
```

If you see a version number (e.g. `PHP 8.2.x`), PHP is already installed.
If not, follow the instructions below.

---

## 2. Installing PHP on macOS

### Option A (recommended): Homebrew

Most students on macOS should use **Homebrew**.

#### Step 1: Install Homebrew (if needed)

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Restart the terminal after installation.

#### Step 2: Install PHP

```bash
brew install php
```

#### Step 3: Verify

```bash
php -v
```

You should see something like:

```
PHP 8.2.x (cli)
```

---

### Where PHP lives on macOS

* Executable: `/opt/homebrew/bin/php` (Apple Silicon)
* Config file: `/opt/homebrew/etc/php/8.2/php.ini`

---

## 3. Installing PHP on Windows

### Option A (recommended): XAMPP (simplest for beginners)

XAMPP bundles **PHP + Apache + MySQL**, which is ideal for learning.

#### Step 1: Download XAMPP

* Download from: [https://www.apachefriends.org](https://www.apachefriends.org)
* Choose a version with **PHP 8.x**

#### Step 2: Install

* Run the installer
* Keep default options (Apache + PHP checked)

#### Step 3: Verify PHP

Open **XAMPP Shell** or **Command Prompt** and run:

```bat
php -v
```

If not recognised:

* PHP is located at: `C:\xampp\php\php.exe`
* You may need to add this to your PATH

---

### Option B (advanced): PHP only

Download PHP from:
[https://windows.php.net/download/](https://windows.php.net/download/)

* Choose **Thread Safe**
* Extract to `C:\php`
* Add `C:\php` to PATH
* Restart terminal

---

## 4. Installing PHP on Linux (Ubuntu / Debian)

```bash
sudo apt update
sudo apt install php php-cli php-common
```

Optional but useful extensions:

```bash
sudo apt install php-curl php-mbstring php-xml php-mysql
```

Verify:

```bash
php -v
```

---

## 5. Running a PHP web server (very important)

PHP includes a **built-in development web server**.

### Step 1: Create a test file

Create `index.php`:

```php
<?php
echo "Hello, PHP!";
```

### Step 2: Start the server

From the directory containing `index.php`:

```bash
php -S localhost:8000
```

### Step 3: Open browser

Visit:

```
http://localhost:8000
```

You should see:

```
Hello, PHP!
```

---

## 6. PHP vs HTML — how they work together

* `.html` → static, served as-is
* `.php` → executed on the server, then HTML is sent to the browser

Example:

```php
<?php
$name = "Student";
?>
<!doctype html>
<html>
<body>
  <h1>Hello <?= $name ?></h1>
</body>
</html>
```

---

## 7. Common problems & fixes

### ❌ `php: command not found`

* PHP not installed or not on PATH
* Restart terminal
* On Windows, ensure `C:\xampp\php` is in PATH

### ❌ PHP code shows as text in browser

* You opened the file directly (`file://`)
* Use `php -S localhost:8000` and access via `http://`

### ❌ Wrong PHP version

* macOS: `brew upgrade php`
* Linux: `sudo apt upgrade php`

---

## 8. Recommended setup for your students

For **first-year undergraduates**, I recommend:

* macOS → Homebrew + PHP built-in server
* Windows → XAMPP
* Linux → apt install php
* Editor → VS Code with:

  * PHP Intelephense
  * PHP Debug (later)

---

## 9. Quick checklist (for a lab handout)

* [ ] `php -v` works
* [ ] `php -S localhost:8000` runs
* [ ] Browser loads `localhost:8000`
* [ ] `.php` files execute correctly

---
