<template>
  <div id="app">
    <Header />
  </div>
</template>

<script>
import Header from './components/Header.vue'

export default {
  name: 'app',
  components: {
    Header
  }
}
</script>

<style>
body {
  text-align: center;
  color: #000000;
  background: #202020;
  margin: 0;
}
</style>
