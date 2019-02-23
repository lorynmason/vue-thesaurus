<template>
  <div id="app">
    <Header />
    <div class="search">
      <input placeholder="find synonyms" v-model="word"/> 
      <button v-on:click="search">SEARCH</button> 
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import { key } from './apikey.js'

export default {
  name: 'app',
  data(){
    return {
      word: '',
      results: []
    }
  },
  components: {
    Header
  },
  methods: {
    async search(){
      const response = await fetch(`https://www.dictionaryapi.com/api/v3/references/thesaurus/json/${this.word}?key=${key}`)
      const results = await response.json()
      const cleanResults = results.map(result => {
        return {
          syns: result.meta.syns,
          def: result.shortdef
        }
      })
      this.results.push(cleanResults)
    }
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

.search {
  margin: 50px auto;
}
input, button {
  margin: 0 15px;
  font-family: 'Special Elite', cursive;
  font-size: 1.2rem;
}

button {
  all: unset;
  font-family: 'Special Elite', cursive;
  background: rgb(145, 145, 145);
  border-radius: 5px;
  padding: 10px;
  box-shadow: -8px 8px 10px black;
  cursor: pointer;
}
</style>
