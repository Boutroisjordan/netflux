<template>

    <div class="card" v-for="post in posts.results" :key="post" >
        <div class="bg-img">
            <img :src="getUrl(post.backdrop_path)">
        </div>

        <h3> {{post.original_title}} </h3>
        
    </div>

</template>

<script>


export default {
    name: "card-netflix",
     methods: {
        async getData() {
            try {
                let res = await fetch('https://api.themoviedb.org/3/movie/popular?api_key=49ecd4647f56c9ac5496c71a9cfe5ba9');
                this.posts = await res.json();
            } catch (error) {
                console.log(error);
            }
        },
        getUrl(pathImg) {
            return this.imageLink + pathImg;
        }
    },
    data() {
        return {
            posts: [],
            imageLink: "https://image.tmdb.org/t/p/original",
        }
    },
    mounted() {
        this.getData();
    }


}


</script>


<style lang="scss" scoped>

.card {
    margin: 0 16px;
    min-width: 450px;
    height: 300px;
    display: flex;
    flex-direction: column;
    justify-content: end;
    padding: 24px 24px;
    margin: 20px 20px;;
    box-shadow: 0px 16px 24px rgba(0, 0, 0, 0.15), 0px 16px 32px rgba(0, 0, 0, 0.1);
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    color: white;
    transition: transform 500ms;
    position: relative;
    overflow: hidden;
}


.card:hover {
  transform: scale(1.2);
  z-index: 1;
}

.bg-img {
        display: flex;
        justify-content: center;
        align-items: center;
        position: absolute;
        width: 100%;
        height: 100%;
    }
    img {
        position: static;
        max-height: 100%;
        object-fit: contain;
    }

    h3 {
        z-index: 3;
    }

// .item:hover {

//   h3 {
//     // transform: translateY(-50px);
//     transition: .5s;
//   }

//   p{
//     display: block;
//     animation: .4s linear dosomething both;
//   }
// }

//  @keyframes dosomething {
//   0% {  
//   opacity: 0;
//   transform: translateY(30px)
//      }
// 100% {  
// 		opacity:1 ;
//     transform: translateY(0px);
//      }
// }


</style>