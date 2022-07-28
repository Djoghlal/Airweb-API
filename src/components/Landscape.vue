<template>

  <video id="background-video" autoplay loop muted>
    <source src="../assets/video/landscape.mp4">
  </video>

</template>

<script>
export default {
    name: 'LandScape',
}
</script>

<style lang="scss">
    #background-video {
        height: 100vh;
        width: 100vw;
        object-fit: cover;
        position: fixed;
        left: 0;
        right: 0;
        top: 0;
        bottom: 0;
        z-index: -1;
    }
</style>