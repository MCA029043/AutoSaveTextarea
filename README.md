
## Auto Save Textarea 

### Step 1: HTML 

Create an HTML file and include the following code:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Auto Save Textarea</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>Auto Save Textarea</h1>
        <textarea id="myTextarea" rows="10" cols="20" placeholder="Start typing here...."></textarea>
    </div>
    <script src="script.js"></script>
</body>
</html>

```

### Step 2: CSS

Create a CSS file and include the following code:

```
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
    padding: 0;
    background-color:#f0f0f0;
}

.container {
    height: 50vh;
    width: 600px;
    padding: 20px;
    background-color: #fff;
    text-align: center;
    margin: 0 auto;
    border-radius: 10px;
    box-shadow: 2px 2px 8px 2px #888888;
}

h1 {
    color: #333;
    font-size: 28px;
    margin-bottom: 20px;
}

textarea {
    width: 100%;
    font-size: 18px;
    border: 2px solid #d4cbcb;
    min-height:180px;
}

textarea:focus {
    border-color: #2fbfb3;
    box-shadow: 0px 0px 5px rgba(29, 126, 96, 0.5);
}


```

### Step 3: JavaScript

Create a JavaScript file and include the following code:

```
const textarea = document.getElementById("myTextarea");

function saveToLocalStorage() {
    localStorage.setItem("savedText", textarea.value);
}

if (localStorage.getItem("savedText")) {
    textarea.value = localStorage.getItem("savedText");
}
textarea.addEventListener("input", saveToLocalStorage);

```

### Step 4: Explanation

The HTML code creates a textarea element with an ID of "myTextarea". The CSS code styles the textarea element. The JavaScript code adds an event listener to the textarea element that saves the textarea's value to local storage every time the user types something. The JavaScript code also loads the saved value from local storage and sets the textarea's value to the saved value when the page loads.
