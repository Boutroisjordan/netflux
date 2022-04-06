// https://www.youtube.com/watch?v=qo4XzJMEMN4 vue3 js carousel

<template>


<h1>NETFLIX</h1>

<h2>Most popular Movies</h2>
<carousel-netflix />
<!-- <card /> -->





</template>

<script>

// import Card from './components/Card.vue'
import carouselNetflix from './components/carouselNetflix.vue'






export default {
  name: 'App',
  components: {
    // Card,
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
}

h1 {
  text-align: center;
  color: red;
}
</style>
