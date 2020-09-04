<template>
  <div id="app">
    <header-top></header-top>
    <contenu></contenu>
  </div>
</template>

<script>

import Header from './components/Header.vue'
import Contenu from './components/Contenu.vue'

export default {
  name: 'App',
  components: {
    'header-top': Header,
    'contenu': Contenu
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
