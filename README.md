# vue-cool-burger

A pure css animated foldout hamburger menu originally made by Erik Terwan turned into a vue component.

## usage

```bash
npm install vue-cool-burger
# or 
yarn add vue-cool-burger
```

then add it to your vue application:

```js
// add it to your vue application:
import VueCoolBurger from 'vue-cool-burger';
import Vue from 'vue';

Vue.use(VueCoolBurger);

// or

import VueCoolBurger from 'vue-cool-burger';

export default {
  components: {
    VueCoolBurger
  }
}
```