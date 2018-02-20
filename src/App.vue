<template>
  <div id="app">
    <h1>Vue.js API</h1>
    <router-view></router-view>
  </div>
</template>

<script>
import Test from './components/Test.vue'
import User from './components/User.vue'
export default {
  name: 'app',
  components: {
    Test,
    User
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>