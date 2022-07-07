<template>
  <div>
    <AppHeader/>
    <div class="main-container">
      <div class="banner-container">
        <Banner/>
      </div>
      <div class="trending-container">
        <Trending/>
      </div>
      <div class="line"></div>
      <div class="all-container" >
        <AllShows :category="current_route"/>
      </div>
    </div>
    <Footer/>
    <button @click="passQuery">hello</button>
  </div>
</template>

<script>
export default {
  data(){
    return{
      all_routes:{
        movies:'discover/movie',
        tv:'discover/tv',
        animation:'discover/movie',
        trending:'trending/all/week'
      },
      current_route:'discover/movie'
    }
  },
  methods:{
    passQuery(){
      console.log(this.all_routes[this.$route.query.category])
    }
  },
  watch:{
    '$route.query'(){
      this.current_route=this.all_routes[this.$route.query.category]
    }
  }

}
</script>

<style scoped lang="scss">
@import '@/assets/scss/_shared.scss';

  .main-container{
    display:flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .banner-container{
    margin:50px 100px 20px 100px;
    height:170px;
    max-width: 1500px;
    min-width:75%;
  }

  .trending-container{
    min-width:calc(80% + 40px);
    margin-left:10%;
    margin-right:10%;
    height:265px;
    border:3px solid $dark-green;
    border-radius: 15px;
  }

  .line{
    margin-top:30px;
    height:0.5px;
    width:100%;
    background-color:gray;
  }

  .all-container{
    min-width: 80%;
    min-height:300px;
  }

</style>