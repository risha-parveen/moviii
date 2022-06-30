<template>
  <header>
    <img src="/moviii_logo.png" alt="moviii logo" width="200px">
  </header>
</template>

<script>
export default {

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
</style>