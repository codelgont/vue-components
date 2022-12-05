<template>
  <MenuComponet msg="Welcome to Your Vue.js App" id="hello"/>
</template>

<script>
import MenuComponet from './components/MenuComponet.vue'

export default {
  name: 'App',
  components: {
    MenuComponet
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
