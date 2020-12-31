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

### props

props shown with `[]` are optional

#### [color] = `'#cdcdcd'`

default color of menu bars

#### [cross-color] = `'#cdcdcd'`

the color of menu bars after transforming into cross

#### [id] = `undefined`

if you want to assign an `id` to the inner checkbox and `for` to the label around it

#### [ariaLabel] = `'main menu'`

#### [expanded] = `false`

should it be rendered in cross form or not

### events

#### expanded: Boolean

emits after the state of menu is changed. emits true if the new state is cross shape.
