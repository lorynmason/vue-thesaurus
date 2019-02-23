<template>
  <div id="app">
    <Header />
    <Search />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Search from './components/Search.vue'

export default {
  name: 'app',
  components: {
    Header,
    Search
  }
}
</script>

<style>
body {
  text-align: center;
  color: #000000;
  background: #2a2a2b;
  margin: 0;
}
</style>
