<template>
  <div class="about">
    <h1>VS</h1>
    <div class="show">
    <button id="right" class="right" v-on:click="game">{{ message }}</button>
    <div id="lift" class="left">svsdvsd</div>
    </div>
  </div>
</template>
<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data: function() {
    var f = 1
    return {message : "Выберете из двух одно"+ f}
  },
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
  background-color: #fff;
}
.left{
  width: 50%;
  height: 100%;
  background-color: rgb(3, 3, 3);
}
</style>