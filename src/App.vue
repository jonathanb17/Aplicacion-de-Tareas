<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <TareaVue/>
  </div>
</template>

<script>
import TareaVue from './components/Tarea.vue'


export default {
  name: 'App',
  components: {
    TareaVue
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
