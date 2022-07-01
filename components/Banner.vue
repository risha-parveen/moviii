<template>
  <div class="banner">
    <img src="spidey.jpg" alt="banner-image">
    <button>Watch Now</button>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped lang="scss">
@import '@/assets/scss/_shared.scss';
  .banner{
    width:100%;
    height: 100%;
    background-color:white;
    overflow:hidden;
    display:inline-block;
    border-radius: 15px;

    img{
      width:100%;
      object-fit:contain;
      object-position: left bottom;
    }

    button{
      padding:10px 20px;
      background-color: $pink;
      border:1px solid pink;
      border-radius:10px;
      color:white;
      font-size: 1.1rem;
      cursor: pointer;

      position: relative;
      top:calc(100% - 60px);
      left:20px;

      &:hover{
        transform: scale(1.02);
        background-color:darken($pink,10);
      }
    }
  }
</style>