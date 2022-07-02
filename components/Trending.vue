<template>
  <div class="trending">
    <p>Trending Shows</p>
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
</template>

<script>
export default {

}
</script>

<style scoped lang="scss">
@import '@/assets/scss/_shared.scss';

.trending{
  width:100%;
  height:100%;
}

p{
  padding:15px 30px;
  margin:0;
  font-family:$font;
  color:$gray;
}

.show-container{
  //width:calc(100% - 40px);
  max-width:730px;
  height:190px;
  padding:0;
  margin:0 20px;
  
  display:flex;
  overflow-x:auto;

  .trending-show{
    height:170px;
    min-width:270px;
    background-color:black;
    border-radius: 15px;;
    margin-right:20px;
  }
}

</style>