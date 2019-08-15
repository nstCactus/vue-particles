# vue-particles
### Vue.js component for particles backgrounds ✨

#### Updated version of Vue Component which optionally accepts a full JSON configuration file of [particles.js](https://github.com/VincentGarreau/particles.js)
Generate a JSON file for use in component [here](https://vincentgarreau.com/particles.js).

## Demo and Usage
_This is the link to the original repo -- not this updated version; the installation instructions are valid as long as you install direct from this repo instead of the npm package (e.g. `npm install git+https://git@github.com/jakekapitz/vue-particles.git --save-dev`)
Link: [http://vue-particles.netlify.com]

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
