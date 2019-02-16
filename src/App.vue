<template>
  <div id="app">
    <LangSon/>
  </div>
</template>

<script>
import LangSon from './components/LangSon.vue'

export default {
  name: 'app',
  components: {
    LangSon
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
