<script>
import Vue from 'vue';
import VueCoolBurger from '@/vue-cool-burger.vue';

export default Vue.extend({
  name: 'ServeDev',
  components: {
    VueCoolBurger,
  },
});
</script>

<template>
  <div id="app">
    <div class="square">
      <VueCoolBurger />
    </div>
  </div>
</template>

<style lang="css">
html {
  background: #232323;
  color: #cdcdcd;
  font-family: 'Avenir Next', 'Avenir', sans-serif;
}

html,
body {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}

#app {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.square {
  width: 50px;
  height: 40px;
}
</style>
