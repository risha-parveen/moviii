<template>
  <div class="banner" @mouseover="showTag" @mouseleave="hideTag">
    <img src="https://www.comingsoon.net/assets/uploads/2012/05/file_90733_0_tdkrnewbannerlarge1.jpg" class="image"/>
    <button>Watch Now</button>
    <p class="movie-tag" v-if="this.tag">The Dark Knight Rises</p>
  </div>
</template>

<script>
export default {
  data(){
    return{
      tag:false
    }
  },

  methods:{
    showTag(){
      this.tag=true;
    },
    hideTag(){
      this.tag=false;
    }
  }
}
</script>

<style scoped lang="scss">
@import '@/assets/scss/_shared.scss';
  .banner{
    width:100%;
    height: 100%;
    background-color:rgb(0, 0, 0);
    border-radius: 20px;;
    display:inline-block;
    position:relative;

    .image{
      width:100%;
      height:100%;
      object-fit: cover;
      object-position:center;
      border-radius: 20px;;
      mask-image: linear-gradient(to bottom, rgb(0, 0, 0) 0%,rgba(0, 0, 0, 0.459) 100%);
      transition: 0.4s ease;
        &:hover{
          mask-image: linear-gradient(to bottom, rgb(0, 0, 0) 0%,rgba(0, 0, 0, 0.212) 100%);

        }
      
    }
    
    
    button{
      padding:10px 20px;
      background-color: $pink;
      border:1px solid pink;
      border-radius:10px;
      color:white;
      font-size: 1.1rem;
      cursor: pointer;

      position: absolute;
      z-index:9;
      top:110px;
      left:20px;

      &:hover{
        transform: scale(1.02);
        background-color:darken($pink,10);
      }
    }

    .movie-tag{
      font-size:1.3rem;
      font-family: $font;
      font-weight: 500;
      position:absolute;
      top:100px;
      left:170px;
      color:$gray;
      cursor:default;
    }
  }
</style>