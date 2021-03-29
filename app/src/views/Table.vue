<template>
  <div class="about">
    <h1>VS</h1>
    <div class="show">
    <div id="left" class="left"  v-on:click="left">
      <img id="img__left" :src="currentPair.img1" />
    </div>
    <div id="right" class="right" @click="right">
      <img id="img__right" :src="currentPair.img2" />
      {{currentPair.img2}}
    </div>
    
    </div>
  </div>
</template>
<script>
export default {
  name: "Table",
  props: {
    msg: String,
  },
  data: function() {
    var f = 1
    return {message : "Выберете из двух одно"+ f,
    currentPair: {img1: 'https://cs4.pikabu.ru/post_img/2014/03/19/10/1395243232_1089834701.jpg',
     img2: 'https://img4.goodfon.ru/wallpaper/nbig/8/70/shchenok-sobachka-boke-kappa-mylnyi-puzyr.jpg'}}
  },
  created() {
    setTimeout(() => {
      this.$emit('test', 12)
    }, 5000)
  },
  mounted() {

  },
  methods:{
    left: function(){
      //console.log(document.getElementById("img__left").src);
      //document.getElementById("img__left").src=logo;
    },
    right: function(){
      console.log("right");
      this.currentPair.img1 = 'https://bipbap.ru/wp-content/uploads/2017/10/07_06_2017_10_08_15_jijtj2ru3nraq07t0u7a9degh0_war6mice03.jpg';
      this.currentPair.img2 = 'https://bipbap.ru/wp-content/uploads/2017/10/00115b52c3100b01ac0a0b.jpg';
    }
  }
};
</script>

<style scoped>
.show{
  display: flex;
  height: 100vh;
}
.right{
  width: 50%;
  height: 100%;
}
.right img,
.left img{
  width: 100%;
}
.left{
  color: #fff;
  width: 50%;
  height: 100%;
}
</style>