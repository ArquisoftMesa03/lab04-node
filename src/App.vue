<template>
  <div id="app">
    <p>¡Bienvenido!</p>
    <request />
  </div>
</template>

<script>
import request from './components/request.vue'

export default {
  name: 'app',
  components: {
    request
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
