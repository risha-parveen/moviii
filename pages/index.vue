<template>
  <div class="container">
    <img src="/big_moviii.png" alt="moviii logo" width="600px">   
      <nuxt-link to="dashboard" >
        <button>Get Started</button>
      </nuxt-link>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
}
</script>

<style lang="scss" scoped>

  @import '@/assets/scss/_shared.scss';
  .container{
    margin-top:250px;
    text-align: center;
    align-items: center;
    display:flex;
    flex-direction: column;

    img{
      padding:0;
    }

    a{
        transition:0.4s ease;
        margin:30px;

        button{
          border-radius: 10px;
          border:none;
          padding:10px 15px;
          transition:0.4s ease;
          background-color:$pink;
          font-size:1.2rem;
          color:white;

          &:hover{
            transform:scale(1.05);
            background-color:darken($pink,10);
          }
        }
      } 
  }
</style>