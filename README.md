# Frontend Mentor - Advice generator app solution

This is a solution to the [Advice generator app challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/advice-generator-app-QdUG-13db). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Frontend Mentor - Advice generator app solution](#frontend-mentor---advice-generator-app-solution)
  - [Table of contents](#table-of-contents)
  - [Overview](#overview)
    - [The challenge](#the-challenge)
    - [Screenshot](#screenshot)
    - [Links](#links)
  - [My process](#my-process)
    - [Built with](#built-with)
    - [What I learned](#what-i-learned)
    - [Continued development](#continued-development)
    - [Useful resources](#useful-resources)
  - [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the app depending on their device's screen size
- See hover states for all interactive elements on the page
- Generate a new piece of advice by clicking the dice icon

### Screenshot

![](/src//assets/active-states.jpg)

### Links

- Solution URL: [https://www.frontendmentor.io/solutions/advice-generator-app-made-with-vuejs-zdnhBkyfAx](https://www.frontendmentor.io/solutions/advice-generator-app-made-with-vuejs-zdnhBkyfAx)
- Live Site URL: [https://admirable-dodol-162f1a.netlify.app/](https://admirable-dodol-162f1a.netlify.app/)

## My process

### Built with

- Semantic HTML5 markup
- CSS
- Flexbox
- Animation
- [Vue](https://vuejs.org/) - Vue.js Framework

### What I learned

- learnt how to add a disabled attribute to a button with vue.
- implemented a timeout/cooldown function for the "dice" button because pulling data from the API was quite slow and if it was clicked in quick succession it was unresponsive.
- learned that an ":enabled"/":disabled" pseudo classes exist and I could use them to alert the user when the button does not work which also improved overall user experience.
- refreshed my memory on how to pull API's in Vue.js
  
```html
<button class="roll" @click="newAdvice(); disableButton();" :disabled="isDisabled">
```

```css
.roll:hover:enabled {
  box-shadow: 0px 0px 24px 0px var(--neong);
}

.roll:disabled{
   background: var(--gblue);
   box-shadow: none;

}
```

```js
//3s cooldown function
 disableButton() {
       this.isDisabled = true;
       setTimeout(() => this.isDisabled = false, 3000);
            console.error('3s cooldown on button')
     },
```


### Continued development

- I need to add responsiveness for phone/tablet devices.
- I had trouble getting the "spin" animation to complete when the button was clicked. My goal was to get the animation to run first and then load the next "advice"

### Useful resources

- [StackOverflow](https://stackoverflow.com/questions/11600687/hover-and-active-only-when-not-disabled) - This helped me understand how to only allow hover states when the button was enabled.
- [Vue Documentation](https://vuejs.org/guide/introduction.html#what-is-vue) - This helped me with general a few problems I was having, nothing particular.

## Author

- Website - [Joshua Steed](https://www.joshuasteed.com)
- Frontend Mentor - [@0xjoshva](https://www.frontendmentor.io/profile/0xjoshva)
