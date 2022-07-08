<template>
  <div class="all-shows" >
    <p>All Shows</p>
    <div class="show-container">
      <div class="show" v-for="show in this.shows.results" :key="show.id">
        <img :src="'https://image.tmdb.org/t/p/w500'+`${show.poster_path}`" :alt="show.title">
        <div class="show-board">
          <p>{{show.title}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async fetch() {
    if(this.$route.query.page) this.page_no=this.$route.query.page
    if(this.$route.query.category) this.current_path=this.all_routes[this.$route.query.category]
    console.log(this.current_path)
    this.shows = await fetch(`
    https://api.themoviedb.org/3/${this.current_path}?api_key=0dd92ad96e0c4b9992f976096e327fb2&inwith_watch_monetization_types=flatrate&page=${this.page_no}`
    ).then((res)=>res.json())
  },
  data(){
    return{
      shows:[],
      page_no:'1',
      current_path:'discover/movie',
      all_routes:{
        movies:'discover/movie',
        tv:'discover/tv',
        animation:'discover/movie',
        trending:'trending/all/week'
      },
    }
  },
}
</script>

<style scoped lang="scss">
@import '@/assets/scss/_shared.scss';

.all-shows{
  width:100%;
  height:100%;
  margin-top:30px;

  p{
    font-family: $font;
    color:white;
    font-size:1.2rem;
    margin-left:30px;
  }

  .show-container{
    width:100%;
    height:100%;
    display:grid;
    gap:3em;
    grid-template-columns: repeat(auto-fit,minmax(300px,1fr));

    .show{
      max-height: 230px;
      background-color:black;
      border-radius: 5px;

      img{
        width:100%;
        height:100%;
        object-fit: cover;
        object-position:center 40%;
        border-radius: 5px;;

      }

      .show-board{
        position:relative;
        bottom: 62px;
        width:100%;
        height:60px;
        margin:0;
        box-shadow: 0 0 1rem 0 rgba(0, 0, 0, .2); 
        border-radius:10px 10px 5px 5px;
        background-color: rgba(255, 255, 255, .15);        
        backdrop-filter: blur(15px);

        p{
          font-weight: bold;
          padding:10px;
          margin:0;
        }

      }

      &:hover{
        transform: scale(1.07);
      }
    }

  }

}

</style>