<template>
  <div id="app" class="container">
    <h1>natofy.io - Vue.js</h1>
    <natofier></natofier>
  </div>
</template>

<script>
import Natofier from './components/Natofier';

export default {
  name: 'app',
  components: {
    Natofier,
  },
};
</script>

<style>
#app {
  text-align: center;
}
</style>
