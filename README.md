# Frontend Mentor - Testimonials grid section solution

This is a solution to the [Testimonials grid section challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/testimonials-grid-section-Nnw6J7Un7). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [How I did it](#how-i-did-it)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size

### Screenshot

![](./design/desktop-design.jpg)

### Links

- Solution URL: [GitHub repository](https://github.com/AyulaBoyilo/FMtestimonialsGrid/)
- Live Site URL: [GitHub Pages](https://ayulaboyilo.github.io/FMtestimonialsGrid/)

## My process

### Built with

- Semantic HTML5 markup
- SCSS and CSS3
- CSS Grid

### How I did it

Rearanged the content for tablet grid to fill the cells optimally. Used a calculated padding for the container at bigger sizes to avoid adding another div, which I would have needed if I used max-width and margin:auto. The px value in the calc expression is the same as the max-width would be. Used fade-out scss module to adjust text tints for colored cards.

```scss
.container {
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: 1fr auto auto auto;
  padding: 10vh calc((100vw - 600px) / 2);

  .primary {
    grid-area: 1 / 1 / 2 / 3;
    background: url(../images/bg-pattern-quotation.svg) no-repeat top 0px right
      100px / 18%;
    background-color: $primary;
  }

  .secondary {
    grid-area: 2 / 1 / 2 / 2;
  }

  .tertiary {
    grid-area: 4 / 1 / 5 / 3;
  }

  .card:last-child {
    grid-area: 2 / 2 / 4 / 3;
  }
}
```

```scss
.primary,
.secondary,
.tertiary {
  color: $default;
  .title {
    color: fade-out($color: $default, $amount: 0.5);
  }
  p {
    color: fade-out($color: $default, $amount: 0.3);
  }
}
```

### Useful resources

- [A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/) - CSS-TRICKS Comprehensive guide to CSS grid.

## Author

- Ayula Boyilo
