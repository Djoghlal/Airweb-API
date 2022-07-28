<template>
  <LandScape/>
  <CompNav/>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import LandScape from './components/Landscape.vue';
import CompNav from './components/Nav.vue';

export default {
  name: 'App',
  components: {
    LandScape,
    CompNav
},
}
</script>

<style lang="scss">

html, body {
  margin: 0;
  padding: 0;
}

#app {
  font-family: 'Roboto', sans-serif;
  margin: 0;
  padding: 0;
}

</style>
