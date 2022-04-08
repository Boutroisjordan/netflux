<template>
<h1>NETFLIX</h1>


<carousel-netflix title="Most Popular Movie" />
<carousel-netflix title="Horror" />
<carousel-netflix title="Comedy" />


</template>

<script>

import carouselNetflix from './components/carouselNetflix.vue'


export default {
  name: 'App',
  components: {
    carouselNetflix,
  },
}
</script>

<style>
body {
    background: #000;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #fff;
  margin-top: 60px;
  width: 100%;
  height: auto;
}

h1 {
  text-align: center;
  color: red;
}
</style>
