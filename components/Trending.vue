<template>
  <div class="main-trending">
    <p>Trending Shows</p>
    <div class="trending">
      <div class="show-container">
        <div class="trending-show"></div>
        <div class="trending-show"></div>
        <div class="trending-show"></div>
        <div class="trending-show"></div>
        <div class="trending-show"></div>
        <div class="trending-show"></div>
        <div class="trending-show"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {

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
          flex-shrink: 0;
          border-radius: 10px;;
        }
      }  
    }
    
  }
</style>