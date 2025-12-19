# Matrix-style Terminal 

Who does not like the movie *The Matrix*? The iconic green-on-black "digital rain" terminal has inspired generations of programmers.

![Matrix Digital Rain](../images/matrix.png)

## Plain Markdown fallback (works everywhere)

If the animated version won't run on your platform, paste this static code block into your Markdown to show a "terminal-looking" snippet:

```bash
guest@neo:~$ whoami
guest
guest@neo:~$ echo "Welcome to command-line 101"
Welcome to command-line 101
guest@neo:~$ ls -la
total 32
-rw-r--r-- 1 guest staff  142 Dec 17  2025 README.md
drwxr-xr-x 6 guest staff  192 Dec 17  2025 lab1
guest@neo:~$ cat README.md
Learning the command line gives you superpowers: navigation, automation, debugging.

# Tips:
 - Start simple: cd, ls, cat, mkdir, rm (careful!)
 - Combine commands with pipes: grep, awk, sed
 - Use the terminal to automate repetitive tasks

guest@neo:~$ 
```


## Command Line Starter Worksheet

**Course:** Web Development / Computing Fundamentals
**Level:** 1st-year undergraduate
**Time:** ~30–40 minutes

---

## Motivation: Why the Command Line?

In films like *The Matrix*, hackers don’t click buttons — they *talk directly to the computer*. While real command-line work is less dramatic, it gives you powerful abilities:

* Navigate your computer quickly
* Inspect files and folders
* Automate repetitive tasks
* Understand how web servers really work

In this worksheet, you’ll practise the **core commands** that underpin web development, servers, and deployment.

---

## Setup (5 minutes)

Open a terminal:

* **macOS:** Terminal app
* **Linux:** Terminal
* **Windows:** WSL (Ubuntu) or Git Bash

You should see a prompt similar to:

```
username@computer:~$
```

---

## Exercise 1: Who and Where Am I? (5 minutes)

Type the following commands, one at a time:

```bash
whoami
pwd
```

**Questions:**

1. What username is printed?
2. What directory are you currently in?
3. What does `~` represent?

---

## Exercise 2: Exploring Files and Folders (5 minutes)

Run:

```bash
ls
ls -l
ls -la
```

**Questions:**

1. What changes when you add `-l`?
2. What extra files appear with `-a`?
3. What do file permissions (e.g. `rw-r--r--`) roughly mean?

---

## Exercise 3: Creating Your First Project (10 minutes)

Create a folder for this course:

```bash
mkdir web-dev
cd web-dev
```

Now create a file:

```bash
echo "Hello, command line" > README.txt
cat README.txt
```

**Questions:**

1. What does `>` do?
2. What does `cat` stand for?
3. Why might this be useful for web projects?

---

## Exercise 4: Searching Like a Hacker (10 minutes)

Add more text:

```bash
echo "The command line gives you superpowers" >> README.txt
echo "Web servers love terminals" >> README.txt
```

Now search inside the file:

```bash
grep "command" README.txt
```

**Questions:**

1. What lines are printed?
2. What happens if you search for a word that doesn’t exist?
3. How might this help when debugging code or logs?

---

## Exercise 5: One-Line Superpowers (5 minutes)

Try this:

```bash
ls -la | grep README
```

```bash
curl https://www.example.com | grep "<title>"
```

```bash
wget -q -O - https://www.example.com | grep "<h1>"
```



**Questions:**

1. What does the pipe symbol `|` do?
2. How is this different from running the commands separately?
3. Why is this powerful for automation?

---

## Challenge (Optional)

Try to:

* Create a folder called `lab1`
* Create a file called `index.html`
* Print its contents to the terminal

*Hint: combine `mkdir`, `cd`, `echo`, and `cat`.*

---


🚀

