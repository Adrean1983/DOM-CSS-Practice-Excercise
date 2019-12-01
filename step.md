# Readme

Taken from Zero-To-Mastery course. Uses DOM to dynamically show a linear gradient background. Pratcice for DOM selectors and event listeners.

## Steps

- 1

  Add css selectors for the elements. These are the h3 and two color inputs.
  Add event listeners that call a function that console logs the value

- 2

  Add a selector for the body, can use create an id in html. When color changes it should update the css of the body.

- 3

  Refactor the code - no DRY. Add the text content of the background to the h3 tag and display

## Solution

- 1

```
let color1 = document.querySelector(".color1");
let color2 = document.querySelector(".color2");
let css = document.querySelectorAll("h3");

color1.addEventListener("input", () => {
console.log(color1.value);
});
color2.addEventListener("input", () => {
console.log(color2.value);
});
```

- 2

```
let color1 = document.querySelector(".color1");
let color2 = document.querySelector(".color2");
let css = document.querySelectorAll("h3");
let body = document.getElementById("gradient");


color1.addEventListener("input", () => {
  body.style.background = `linear-gradient(to right, ${color1.value}, ${color2.value})`;
});

color2.addEventListener("input", () => {
  body.style.background = `linear-gradient(to right, ${color1.value}, ${color2.value})`;
});
```

- 3

```
let color1 = document.querySelector(".color1");
let color2 = document.querySelector(".color2");
let css = document.querySelectorAll("h2");
let body = document.getElementById("gradient");

setGradient = () => {
  body.style.background = `linear-gradient(to right, ${color1.value}, ${color2.value})`;
  css.textContent = body.style.background;
};

color1.addEventListener("input", setGradient);
color2.addEventListener("input", setGradient);
```
