<template>

<h2>{{ title }}</h2>

<div class="slidde">

    <card-netflix />
</div>

</template>

<script>
import cardNetflix from './Card.vue';

export default {
    props: ['title'],
    name: 'carousel-netflix',
    components: {
        cardNetflix,
    },
    data() {
        return {
            textHeader: ""
        }
    }
}
   


</script>

<style lang="scss" scoped>


h2 {
    margin: 0 24px;
}
.wrapper {
    width: 95%;
    margin: 0 auto;
}


.slidde {
    width: auto;
    height: 500px;
    display: flex;
    align-items: center;
    flex-direction: row;
    overflow-x: scroll;
}



.slidde::-webkit-scrollbar {
    opacity: 0;
}

</style>
