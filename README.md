# Frontend Mentor - Single price grid component solution

This is a solution to the [Single price grid component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/single-price-grid-component-5ce41129d0ff452fec5abbbc). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Useful resources](#useful-resources)
- [Author](#author)
  - [Contact](#contact)


## Overview

### The challenge

Users should be able to:

- View the optimal layout for the component depending on their device's screen size
- See a hover state on desktop for the Sign Up call-to-action

### Screenshot

![](./images/mobile-view.png)
![](./images/desktop-view.png)

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [single-price-grid-component](https://single-price-grid-component-five-gules.vercel.app/)

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- Fluid Typography

## My process

Because this project rely on changing the layout of the grid based on a breakpoint I decided to learn more about css grid before start this project.

I used a template from [Kevin powell](https://github.com/kevin-powell/learn-grid-the-easy-way/tree/main) (he used a chanllenge from FEM btw) that he builded for his [Youtube video](https://www.youtube.com/watch?v=rg7Fvvl3taU&t=181s) where he show how to use the [grid-template-areas](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas) to make styling complex grid layout more easy.

This is my repository I created to leran [learn-css-css-grid-the-easy-way](https://github.com/jonatasolmartins/learn-css-grid-the-easy-way/tree/master) and [this](https://learn-css-grid-the-easy-way.vercel.app/) is the live site.

### What I learned

I learned how to make my site responsive with a fluid typography for my font-size, margi and padding.

#### The font-size will grow or shrink in a fluid manner based on the width viewport of the device.
```css
:root {
   --fs-400: clamp(0.94rem, 3vw + 1rem, 1.25rem);
}
```
I also put in practice everything I've leran about grid-template-area.

## Example


```html
<main class="join-community-grid">
    <section class="join-community-card">
      <div class="header">
        <p>
          Lorem Lorem
        </p>
      </div>
    </section>
     <section clas="join-community-card">
       <div class="plan-card">
        <p>
          Lorem Lorem
        </p>
      </div>
    </section>
     <section class="join-community-card">
      <div class="why-us">
        <p>
          Lorem Lorem
        </p>
      </div>
    </section>
</main>
```

To use the grid-template-areas you first make your container a grid and then you give a name for each item on the grid.

```css
.join-community-grid {
    display: grid;
    grid-auto-columns: 1fr;
    grid-template-areas: 
    "header"
    "plan-card"
    "why-us";
    max-width: 635px;
    box-shadow: 0px 15px 30px 0px rgba(0, 81, 171, 0.15);
    border-radius: 0.5rem 0.5rem 0.5rem 0.5rem;
}
```

Them we set the names for each item on the grid.
I used nth-child because it easy doing like that.

```css
.join-community-card:nth-child(1) {
    grid-area: header;
}

.join-community-card:nth-child(2) {
    grid-area: plan-card;
}

.join-community-card:nth-child(3) {
    grid-area: why-us;
}

.....

```
At this moment we're done.
We can change the layout of the grid based on the media query if we want, we can also increaseor decrease the number of column and rows and also change the position of the grid items.

### Two columns and 2 rows
The header item will use two columns and the others items will use one column each.

```css
@media screen and (min-width: 43em) {
  .join-community-grid  {
        grid-template-areas: 
        "header header"
        "plan-card why-us";
    }
}
```



### Three columns and 3 rows
Also changes the order of the items in the grid

```css
@media screen and (min-width: 50em) {
  .testimonial-grid {
      grid-template-areas:
      "header header why-us"
      "plan-card plan-card"
      "plan-card plan-card";
  }
}
```

## Conclusion
It was very fun styling it by myself, I learn a lot in the process, and with no doubt the [grid-template-areas](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas) is easier to use and maintan the code as well.

### Continued development

This was my first attempt to use utilities classes on the project and I plan to continue studing about this approach.

### Useful resources

- [Youtube video](https://www.youtube.com/watch?v=rg7Fvvl3taU&t=181s) - This video from Kevin powell helped me understand how to use grid-template-area on this project.
- [Css-Tricks article](hhttps://css-tricks.com/linearly-scale-font-size-with-css-clamp-based-on-the-viewport/) - This is an amazing article which helped me finally understand how to calculate the secound value (preferred size) on a clamp function, now my site has a fluid typography. I'd recommend it to anyone still learning this concept.

## Author

### Contact
- Frontend Mentor - [@jonatasolmartins](https://www.frontendmentor.io/profile/jonatasolmartins)
- Linkedin- [Jonatas Martins](https://www.linkedin.com/in/jonatas-ol-martins-038a9513/)
- Github [jonatasolmartins](https://github.com/jonatasolmartins)
