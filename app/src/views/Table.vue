<template>
  <div class="about">
    <h1>VS</h1>
    <div class="show">
    <div id="left" class="left"  v-on:click="left">
      <img id="img__left" src="../assets/1.jpg" />
    </div>
    <div id="right" class="right" v-on:click="right">
      <img id="img__right" src="../assets/logo.png" />
    </div>
    
    </div>
  </div>
</template>
<script>
import logo from "../assets/logo.png"
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data: function() {
    var f = 1
    return {message : "Выберете из двух одно"+ f}
  },
  methods:{
    left: function(){
      document.getElementById("img__left").src=logo;
    },
    right: function(){
      console.log("right");
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