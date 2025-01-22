---
layout: project
type: project
image: img/personal/personal-logo.png
title: "Personal Portfolio"
date: 2024-12-22
published: true
labels:
  - HTML/CSS
  - JavaScript
  - GitHub
  - Visual Studio Code
summary: "My personal website developed from scratch using HTML/CSS."
---

<img class="img-fluid" src="../img/personal/personal-home.png">

This personal portfolio is my first full project implementing HTML, CSS, and JavaScript using the Visual Studio Code IDE and GitHub for deployment. I intend to maintain this website and develop it alongside my professional portfolio. Contents of the website include an 'About' section detailing a short introduction, an interactive 'Experience' section that employs JavaScript to display my work from different years, 'Projects' which links to a different page, and a 'Contact' form at the end. It currently displays multiple HTML form elements, links, and feedback is returned from the form via email to a business account. The website was made with an emphasis on **interactivity** and **style**.

By embarking on an independent project with little-to-no experience in HTML, CSS, or JavaScript, I was able to learn "how to learn" and develop skills independent of a school/work setting by reading documentation, viewing tutorials, and testing code. Furthermore, I began to understand the thought process and considerations of front-end developeent while becoming familiar with the Visual Studio Code environment and extensions to facilitate this development.

Here is a script to change the displayed elements from my 'Experience' section.

```javascript
function swapLeft() {
    var years = document.querySelectorAll("input[name='year']");

    var target = document.querySelector("input[name='year']:checked");
    var rootNode = document.getElementById(target.id).parentElement.parentElement;
    var replacement = parseInt(rootNode.id[rootNode.id.length - 1]) + 1
    var leftNode = document.getElementById(rootNode.id.replace(/.$/, replacement));

    if (target == years[0]) {
        target = years[years.length-1];
        rootNode = document.getElementById(target.id).parentElement.parentElement;
        leftNode = document.getElementById(rootNode.id);
    }

    swapDiv(leftNode);
}
```

View the latest version of my [personal portfolio](https://aar0m.github.io/personal/).