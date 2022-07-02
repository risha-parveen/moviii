<template>
  <div class="banner">
    <img src="spidey.jpg" class="image"/>
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
    border-radius: 20px;;
    display:inline-block;
    position:relative;

    .image{
      width:100%;
      height:100%;
      object-fit: cover;
      object-position:center 60%;
      border-radius: 20px;;
      mask-image: linear-gradient(to bottom, rgb(0, 0, 0) 0%,rgba(0, 0, 0, 0.356) 100%);
      transition: 0.4s ease;

      &:hover{
        mask-image: linear-gradient(to bottom, rgb(0, 0, 0) 0%,rgba(0, 0, 0, 0.514) 100%);
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
  }
</style>