<template>
  <div class="footer">
    <div class="button-container">
      <button v-for="item in buttons" :key="item.name"
        @click="buttonClick(item.name)"
        :class="{clicked:active===`${item.name}`}"
      >
        {{item.name}}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      buttons:[
        {name:'1'},
        {name:'2'},
        {name:'3'},
        {name:'4'},
        {name:'5'},
      ],
      active:'1',
    }
  },
  methods:{
    buttonClick(btn_number){
      this.active=btn_number
      this.$router.push({path:'/dashboard',query:{page:`${btn_number}`}});
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

.footer{
  margin:20px;
  padding:10px;
  .button-container{
    display:flex;
    flex-direction: row;
    float: right;

    button{
      padding:6px 10px;
      background-color:$gray;
      color:black;
      font-size:1.1rem;
      border:1px solid black;
      border-radius: 3px;
      margin:3px;
    }

    .clicked{
      background-color:rgb(99, 89, 89);
      color:white;
      font-weight: bold;
    }
  }
}
</style>