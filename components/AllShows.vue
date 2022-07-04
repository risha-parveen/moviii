<template>
  <div class="all-shows">
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
  data(){
    return {
      shows:[]
    }
  },
  async created(){
    const res = await fetch(`https://api.themoviedb.org/3/discover/movie?api_key=0dd92ad96e0c4b9992f976096e327fb2&with_genres=878&include_adult=true`)
    
    this.shows=await res.json()
  }
}
</script>

<style scoped lang="scss">
@import '@/assets/scss/_shared.scss';

.all-shows{
  width:100%;
  height:100%;
  padding:10px;

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
      max-height: 200px;
      background-color:black;
      border-radius: 5px;

      img{
        width:100%;
        height:100%;
        object-fit: cover;
        object-position:center;
        border-radius: 5px;;
      }

      .show-board{
        position:relative;
        bottom:81px;
        width:100%;
        height:60px;
        box-shadow: 0 0 1rem 0 rgba(0, 0, 0, .2); 
        border-radius:10px 10px 5px 5px;
        background-color: rgba(255, 255, 255, .15);        
        backdrop-filter: blur(15px);
        
      }

      &:hover{
        transform: scale(1.07);
      }
    }

  }

}

</style>