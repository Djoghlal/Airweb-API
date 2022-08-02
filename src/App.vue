<template>
  <LandScape/>
  <CompHeader/>
  <ViewMain/>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import LandScape from './components/Landscape.vue';
import CompHeader from './components/Header.vue';
import ViewMain from './views/Main.vue';

export default {
  name: 'App',
  components: {
    LandScape,
    CompHeader,
    ViewMain
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
