# vue-particles

## ✨ Vue.js Component for Particle Backgrounds ✨

#### Updated version of Vue Component which optionally accepts a full JSON configuration file of [particles.js](https://github.com/VincentGarreau/particles.js)

Generate a JSON file for use in component [here](https://vincentgarreau.com/particles.js).

### Demo and Usage

Link: [http://vue-particles.netlify.com]

The demo is of the original repo. The installation instructions are valid as long as you install direct from this repo instead of the npm package:

`npm install git+https://git@github.com/jakekapitz/vue-particles.git --save-dev`

### Single File Component Usage

In your `.vue` component:

```JavaScript
<template>
  <div>
    <vue-particles :particlesData="particlesSetup"></vue-particles>
  </div>
</template>

<script>
import json from 'path-to-your-particlesjs-config.json'

export default {
  data() {
    return {
      particlesSetup: json
    }
  }
}
```

------------------------------

### Particles displaying on top of your other elements?

Easily fixed via CSS (below is adding a utility class a la TailWindCSS but you're free to do as you please 😁):
  
```javascript
<template>
  <vue-particles class="z-minus"></vue-particles>
</template>

<script>
...
</script>

<style>
.z-minus {
  z-index: -1;
}
</style>
```

If you get your particles behind your other content correctly but your mouse events don't work over the entire page (i.e. they stop when you mouse over your content), you're going to want to change your configuration file to:

```json
..."interactivity": {
     "detect_on": "window" // defaults to "canvas"
```

### SSR compatible - Tested with <a href="https://nuxtjs.org/" target="_blank">Nuxt.js</a>
For Nuxt.JS and & SSR ensure your `nuxt.config.js` is configured per the below:

```JavaScript
plugins: [
  {
    src: '~/plugins/vue-particles',
    mode: 'client'
  }
]
```

If this fails, try wrapping the `<vue-particles>` component with a `<no-ssr>` tag. ¯\_(ツ)_/¯

------------------------------
