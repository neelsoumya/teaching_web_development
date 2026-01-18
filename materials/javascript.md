# JavaScript

JavaScript is a versatile, high-level programming language primarily used for web development. It enables interactive web pages and is an essential part of web applications. Alongside HTML and CSS, JavaScript is one of the core technologies of the World Wide Web.

## Resources

- [video on javascript by Dr. Severance part 1](https://youtu.be/AyIllqHSGoI?si=_loaUr0YDf5J0w0p)

- [video on javascript by Dr. Severance part 2](https://youtu.be/E5jTKLXz9OE?si=E7Zkq6LXHmgBv-4g)


## 🛠️ Example code (practical)

- Here is some javascript code

```html
<script type="text/javascript">
        document.write("<p> Hello from the world of Javascript</p>")
</script>  

<noscript> This browser does not support Javascript. Yikes!
</noscript>  
```

- You can also write this in a separate javascript file

```html
<script type="text/javascript" src="call.js">
</script>  

<noscript> This browser does not support Javascript. Yikes!
</noscript>  
```


- The full code is here:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content = "width=device-width, initial-scale=1.0">
  <title> CSS and HTML practice </title>
  </head>

  <body>
    <header id ="main-header-page">
      <h1 class="title">
        Welcome to HTML!
      </h1>  
    </header>

    <main>
        <section class="content">
            <h2> This is a header </h2>
            <p> This is a paragraph </p>
            <a href="https://neelsoumya.github.io/" class="link">My webpage link</a>
        </section>        
    </main>    

    <script type="text/javascript">
        document.write("<p> Hello from the world of Javascript</p>")
    </script>  

    <noscript> This browser does not support Javascript. Yikes!
    </noscript>  

    <footer class="footer">
      <p> This is a test footer </p>
    </footer>   

  </body>  

</html>

```

## Dialog box

- `alert`

```html
alert("This is a dialog box")
```


## Javascript fails silently

- Fail silently

- Move on to the next tags

## Useful commands

- `console.log("Hello from console")`

  - 💡 will only show in developer console

- can also do 

```html
window.console & console.log("Hello from console")
```

- 💡 can have breakpoints in developer console in browser

- comments `//`

- string concatenation

```html
x = 12 + "hello";
```

- functions

- use `var` for scoping local

```html
<script>
  gl = 123;

  function check(){
    var gl = 456;
  }

  check(); // call function

  console.log("Value of gl is:", gl);

</script>
```


- arrays

```html
<script>
  toys = ['bat', 'ball', 'lego'];
  console.log(toys[1]);
</script>  
```

- associative arrays

```html
<script>
  b = {"name":"chuck", "age":76};
  console.log(b);
</script>  
```

- `NaN` . It is also _sticky_.

- ⚠️ _NOTE_ Scope is global by default! See this [video](https://youtu.be/E5jTKLXz9OE?si=RC_5cJyNFLVxVO7_)


## 🎮 Exercise (try this in your browser)

- Use [jsfiddle.net](https://jsfiddle.net/) to try the following code

```html
<head>
  <script type="text/javascript">
    function calc(radius){
      var circum = 2 * Math.PI * radius;
      return circum;
    }
  </script>
</head>

<body>
  <form name="myForm">
    <input type="text" name="answer"/>
    <br/>
    <input type="button" value="calculate circumference" onclick="document.myForm.answer.value=calc(70);">
  </form>  
</body>
```


## 🧩🚀 Javscript is used to modify the DOM

- DOM = Document Object Model