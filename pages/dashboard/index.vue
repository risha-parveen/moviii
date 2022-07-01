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
      <div class="all-container">
        <AllShows/>
      </div>
    </div>
    <Footer/>
  </div>
</template>

<script>
export default {

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
    background-color:gray;
    margin:50px 100px 20px 100px;
    height:170px;
    max-width: 1500px;
    min-width:75%;
    border-radius: 20px;
  }

  .trending-container{
    min-width:80%;
    height:300px;
    border:1px solid $dark-green;
    border-radius: 15px;
  }

  .all-container{
    min-width: 80%;
    min-height:300px;
    background-color:black;
  }

</style>