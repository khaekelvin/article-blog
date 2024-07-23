---
title: "How a Browser renders a page for a user"
description: "How a Browser renders a page for a user"
date: "2023-08-11"
---

![](https://media.dev.to/cdn-cgi/image/width=1000,height=420,fit=cover,gravity=auto,format=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fe4zt6ry049i65z0sm56v.png)

In this article I explain the steps your browser takes to convert HTML, CSS, and JavaScript into a working website you can interact with.

## Process

### • Receiving the HTML document and Constructing the DOM:

![html](https://res.cloudinary.com/practicaldev/image/fetch/s--8YXZBAv4--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/f9e0xiib5qtvws8fxdid.png)

### • Parsing The HTML

In this step the browser receives the HTML file and changes its format into a readable form for the user to understand.

```html
<html>
  <head>
    <script src="index.js"></script>
    <link rel="stylesheet" href="style.css" />
    <title>Document</title>
  </head>

  <body>
    <div>
      <p>Sample 1</p>
      <p><span class="text">Sample 2</span></p>
    </div>
  </body>
</html>
```

### • Fetching External Files:

![files](https://res.cloudinary.com/practicaldev/image/fetch/s--k4560tyF--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/le0p3htvuggy72c165eh.png)

```javascript
<script src="index.js"></script>
<link rel="stylesheet" href="style.css" />
```

### • Applying CSS:

![](https://res.cloudinary.com/practicaldev/image/fetch/s--VZq22VMF--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/xarbd3giolac4hvb6v4l.png)

```css
body {
    font-size: 5px;
}

p {
    font-weight: bolder;
}

.text {
    color: red;
}
```

CSS has something called the cascade. The cascade is how the browser determines what styles are applied to an element.
This is important because the browser has to recursively go through the CSS tree structure and determine the styles that affect a particular element.

### • The Render Tree:

![](https://res.cloudinary.com/practicaldev/image/fetch/s--W-3ciJT7--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/t35frql7ziw69v295ae8.png)

### • Layout:

![](https://res.cloudinary.com/practicaldev/image/fetch/s--ZaQm5Clm--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/q2tn6lhobvethumdcz7s.png)

### • Painting:

![](https://res.cloudinary.com/practicaldev/image/fetch/s--y3FDMQHk--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/xveaafo4lukgv11286kj.png)

### • JavaScript:

Most modern websites contain JavaScript now so the browser will have to fetch its files and execute it after rendering the page. JavaScript adds interactivity to the page to enhance user experience. It can trigger animations and fetch data. JavaScript can also remove and add elements from the DOM tree, and you may modify the CSSOM properties of an element via JavaScript as well.

In conclusion, the process of how a browser renders a webpage is complex, involving different components within the browser. From parsing and constructing the DOM to applying CSS styles, calculating layouts, and executing JavaScript, each step plays a vital role in transforming raw code into the visually appealing and interactive web pages we interact with daily