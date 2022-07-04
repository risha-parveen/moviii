<template>
  <div class="main-trending">
    <p>Trending Shows</p>
    <div class="trending">
      <div class="show-container">
        <div class="trending-show" v-for="show in this.shows.results" :key="show.id">
          <img :src="'https://image.tmdb.org/t/p/w500'+`${show.poster_path}`" :alt="show.title">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      shows:[]
    }
  },
  async created(){
    const res = await fetch(`https://api.themoviedb.org/3/trending/all/day?api_key=0dd92ad96e0c4b9992f976096e327fb2&with_genres=878&include_adult=true`)
    
    this.shows=await res.json()
  }

}
</script>

<style scoped lang="scss">
@import '@/assets/scss/_shared.scss';

  .main-trending{
    font-family: $font;   
      
    p{
      color:white;
      padding:0px 30px;
      font-size:1.2rem;
    }
    .trending{
      overflow-x:auto;
      overflow-y:hidden;
      margin:10px;

      .show-container{
        height:170px;
        width:700px;
        display:flex;
        
        .trending-show{
          background-color:black;
          height:100%;
          width:260px;
          margin-inline: 20px;
          padding:1px;
          flex-shrink: 0;
          border-radius: 10px;;

          img{
            width:100%;
          height:100%;
          object-fit: cover;
          object-position:center;
          border-radius: 10px;;
          }
        }
      }  
    }
    
  }
</style>