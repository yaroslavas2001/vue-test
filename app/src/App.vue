<template>
  <div id="app">
    <Table name="dfbdfbfdb"/>
    <input type="text" class="input">

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Table from './components/Table.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    Table
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #000;
  margin: 60px;
}
.input{
  margin-top: 20px;
}
</style>
