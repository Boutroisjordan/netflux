<template>
<div class="wrapper">
    <vueper-slides
  class="no-shadow"
  :visible-slides="3"
  slide-multiple
  :gap="3"
  :slide-ratio="1 / 4"
  :dragging-distance="100"
  :breakpoints="{ 800: { visibleSlides: 2, slideMultiple: 2 } }">

  <vueper-slide 
    v-for="post in posts.results" 
    :key="post"
    :content="post.original_title"
    :style="'background-image:' + `url(https://image.tmdb.org/t/p/original${post.backdrop_path})`"/>



</vueper-slides>
</div>


</template>

<script>

import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'


export default {
    name: 'carousel-netflix',
    components: {
        // Card,
        VueperSlides,
        VueperSlide,


    },
    methods: {
        async getData() {
            try {
                let res = await fetch('https://api.themoviedb.org/3/movie/popular?api_key=49ecd4647f56c9ac5496c71a9cfe5ba9');
                this.posts = await res.json();
            } catch (error) {
                console.log(error);
            }
        }
    },
    data() {
        return {
            posts: [],
        }
    },
    mounted() {
        this.getData();
    }

}


</script>

<style lang="scss" scoped>


.wrapper {
    width: 95%;
    margin: 0 auto;
}

.vueperslide {
    font-size: 2rem;
    display: flex;
    flex-direction: column;
    justify-content: end;
}


</style>