<template>
  <div>
    <LandScape/>
    <CompHeader/>
    <router-view/>
  </div>
</template>

<script>
import LandScape from './components/Landscape.vue';
import CompHeader from './components/Header.vue';

export default {
  name: 'App',
  components: {
    LandScape,
    CompHeader,
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
