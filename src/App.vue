<template>
  <router-view/>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@200;300;400;500;600;700;800&display=swap');
/* font-family: 'Manrope', sans-serif; */

*, *::before, *::after {
  box-sizing: border-box;
}
* {
  margin: 0;
}
html, body {
  height: 100%;
}
body {
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
}
img, picture, video, canvas, svg {
  display: block;
  max-width: 100%;
}
input, button, textarea, select {
  font: inherit;
}
p, h1, h2, h3, h4, h5, h6 {
  overflow-wrap: break-word;
}
#root, #__next {
  isolation: isolate;}

:root{
 /* primary */
  --lcyan: hsl(193, 38%, 86%);
  --neong: hsl(150, 100%, 66%);

  /* neutral */
  --gblue: hsl(217, 19%, 38%);
  --dgblue: hsl(217, 19%, 24%);
  --dblue: hsl(218, 23%, 16%);
  }
</style>
