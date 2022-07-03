<template>
  <div class="all-shows">
    <p>All Shows</p>
    <div class="show-container">
      <div class="show">
        <img src="https://akm-img-a-in.tosshub.com/indiatoday/images/story/202205/doctor-strange-multiverse-of-m_1200x768.jpeg?YDKJbvufDCOvrdJyvnVzY_qp8.LJVlc0&size=770:433" alt="dr strange">
      </div>
      <div class="show">
        <img src="https://i.ytimg.com/vi/YF1eYbfbH5k/maxresdefault.jpg" alt="interstellar">
      </div>
      <div class="show">
        <img src="https://i.ytimg.com/vi/XcCWBRqWmyw/maxresdefault.jpg" alt="bhramastra">
      </div>
      <div class="show">
        <img src="https://images.newindianexpress.com/uploads/user/imagelibrary/2021/9/9/w1200X800/Mammootty.jpg" alt="bheeshma">
      </div>
      <div class="show">
        <img src="https://images.indianexpress.com/2021/12/minnal-murali-review-.jpg" alt="minnal">
      </div>
      <div class="show">
        <img src="https://www.soda.com/wp-content/uploads/2020/04/harry-potter-streaming-guide-600x361.jpg" alt="hp">
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
  }
}
</script>

<style scoped lang="scss">
@import '@/assets/scss/_shared.scss';

.all-shows{
  width:100%;
  height:100%;

  p{
    font-family: $font;
    color:white;
  }

  .show-container{
    width:100%;
    height:100%;
    display:grid;
    grid-gap:3em;
    grid-template-columns: repeat(auto-fit,minmax(300px,1fr));

    .show{
      max-height: 200px;
      background-color:black;
      border-radius: 15px;

      img{
        width:100%;
        height:100%;
        object-fit: cover;
        object-position:center;
        border-radius: 20px;;
      }
    }
  }

}

</style>