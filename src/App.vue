<template>
<gene-password></gene-password>

</template>

<script>

import genePassword from './components/GenePassword.vue'
export default {
  name: 'App',
  components: {
    genePassword
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
