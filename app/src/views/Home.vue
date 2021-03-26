<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <div id="components-demo">
    <button-counter>кнопкп</button-counter>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
  },
};
Vue.component('button-counter', {
  data: function () {
    return {
      count: 0,
    };
  },
  template: '<button v-on:click="count++"> Счётчик кликов — {{ count }} </button>'
});
</script>
