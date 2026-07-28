# Frontend Mentor - Meet landing page solution

This is a solution to the [Meet landing page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/meet-landing-page-rbTDS6OUR). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
    - [The challenge](#the-challenge)
    - [Screenshot](#screenshot)
    - [Links](#links)
- [My process](#my-process)
    - [Built with](#built-with)
    - [What I learned](#what-i-learned)
    - [Continued development](#continued-development)
    - [Useful resources](#useful-resources)
    - [AI Collaboration](#ai-collaboration)
- [Author](#author)
- [Acknowledgments](#acknowledgments)


## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements

### Links

- Live Site URL: [Meet Landind Page](https://andreajrujano.github.io/fem-meet-landing-page/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow

### What I learned

#### Decorative content that can be achieved via CSS

There are decorative content that can be achieved via CSS such as

- the number circles with the thin vertical line are just decorative, they were hidden via `aria-hidden="true"` attribute
- The images in the hero were added via `background-image` in css
- The feature images were added in the html but with `alt=""` since they do not add information

#### Pseudo-elements `::before` and `::after` inherit flex display

The html for the number in circles is
```html
<div aria-hidden="true" class="section-number"><span>02</span></div>
```
and the styling via css is

```css
.section-number{
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.section-number::before {
    content: "";
    background-color: var(--slate-300);
    width: 1px;
    height: 80px;
}
```

Since the class `section-number` has flex display the pseudo-element `::before` behaves as a flex item. This is why the thin line (or rectangle) sits on top of the circle.

Note: to achieve the circle, it was target the `span` element inside the element `div.section-number`. 

#### Hero images added using pseudo-elements

Hero images were added using the pseudo-elements `::before` and `::after`, for the mobile and tablet version it was only needed the `::before`since the image is on top of the hero text.

Through media queries, it was replace the `::before` element with the left side image of the hero and the right side was added through `::after`.

#### Flex items default behavior is `stretch`

ffsdf

#### Make the body to get the leftover space

The `body` was turned into a flex container, within it has children: `header`, `main` and `footer`. They `body` is as tall as its content, so it end up having some leftover space _below_ the footer, when the footer should always sit at the bottom of the page.

To make the `main` element absorb all the leftover space, pushing the footer to the bottom, it was used the `flex-grow`property, which defaults value is 0. That is, all items grow the same, but by giving the value 1 to the `main` element, this elements grows more than the rest.

```css
main {
    flex-grow: 1;
}
```

### Useful resources

- [MDN docs](https://developer.mozilla.org/en-US/) - Used to search properties and their possible values

