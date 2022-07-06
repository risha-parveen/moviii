<template>
  <div>
    <pre style="color:white;">{{post.page}}</pre>
    <button @click="meth">butt1</button>
    <button @click="meth">butt2</button>
    <button @click="meth">butt3</button>
  </div>
</template>

<script>
export default {
  async asyncData({ params, $axios }) {
    const post = await $axios.$get(`https://api.themoviedb.org/3/discover/movie?api_key=0dd92ad96e0c4b9992f976096e327fb2&language=en-US&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&with_genres=animation,comedy&with_watch_monetization_types=flatrate`)
    console.log(post)
    return { post }
  },
  data(){
    return{

    }
  },
  methods:{
    meth(){
      this.$router.push({path:'/dashboard',query:{page:'4'}});
    }
  },
  
}
</script>

<style>
  button{
    padding:1rem;
  }
</style>