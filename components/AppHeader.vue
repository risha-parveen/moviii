<template>
  <header>
    <div class="header-container">
      <img src="/moviii_logo.png" alt="moviii logo" width="200px">
      <div class="category-container">
        <span @click="categoryClicked('movies')">Movies</span>
        <span @click="categoryClicked('tv')">TV Shows</span>
        <span @click="categoryClicked('animation')">Animation</span>
        <span @click="categoryClicked('trending')">Trending</span>
      </div>
      <div class="account-container">
        <fa :icon="['fas','house']" class="icon-class"/>
        <fa :icon="['fas', 'magnifying-glass']" class="icon-class"/>
        <fa :icon="['fas', 'circle']" class="icon-class" id="circle" />
        <fa :icon="['fas', 'angle-down']" class="icon-class" id="angle-down"/>
      </div>
    </div>    
  </header>
</template>

<script>
export default {
  data(){
    return{
      
    }
  },
  methods:{
    categoryClicked(current){
      this.$router.push({path:'/dashboard',query:{category:`${current}`}});
    }
  },
  watch:{
    '$route.query'(){
      this.$nuxt.refresh()
    }
  }
}
</script>

<style scoped lang="scss">
  @import '@/assets/scss/_shared.scss';
  header{
    background-color:$bgcolor;
    border-bottom:0.2px solid $dark-green;
    border-image:linear-gradient(45deg,$dark-green, $pink);
    border-image-slice: 0.5;

    img{
      margin:20px 30px 0px 60px;
    }
  }

  .head-container{
    position:fixed;
    top:0;
    width:100%;
  }

  .category-container{
    display:inline-block;

    span{
      color:white;
      cursor: pointer;
      font-family:$font;
      font-size:1.2rem;
      font-weight:400;
      margin-right:15px;
      position:relative;
      top:-22px;
      transition:0.5s ease;

      &:hover{
        color:lighten($pink,20);
      }
    }
  }

  .account-container{    
    overflow: hidden;
    float:right;
    margin:52px 60px 0 10px;
    padding:10px;
    cursor:default;

    .icon-class{
      color: lighten($gray,10);
      font-size:1.3rem;
      margin-right:25px;
      transition:0.3s ease;
      cursor:pointer;
      
      &:hover{
        color:darken($gray,20);
      }
    }

    #circle{
      color:#B25656; 
      font-size:1.8rem;
      position:relative;
      bottom:-2px;
      margin-right:5px;
      cursor:default;
    }

    #angle-down{
      font-size: 1rem;
      margin:0;
    }
  }
</style>