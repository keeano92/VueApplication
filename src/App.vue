<template>
  <div id="app">
      <!-- TODO: Add video background loop -->
    <img src="./assets/logo.png">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<!-- Removed in production -->
<style>
#app {
   font-family: 'Avenir', Helvetica, Arial, sans-serif;
   -webkit-font-smoothing: antialiased;
   -moz-osx-font-smoothing: grayscale;
   text-align: center;
   color: #2c3e50;
   margin-top: 60px;
 }

 #background_video {
     position: fixed;
     right: 0;
     bottom: 0;
     min-width: 100%;
     min-height: 100%;
 }
</style>
