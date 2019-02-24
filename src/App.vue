<template>
  <div id="app">
    <Header />
    <div class="search">
      <input placeholder="find synonyms" v-model="word"/> 
      <button v-on:click="search">SEARCH</button> 
    </div>
    <CardContainer :results="results" :word="word"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import { key } from './apikey.js'
import CardContainer from './components/CardContainer.vue'

export default {
  name: 'app',
  data(){
    return {
      word: '',
      results: []
    }
  },
  components: {
    Header,
    CardContainer
  },
  methods: {
    async search(){
      this.results = []
      const response = await fetch(`https://www.dictionaryapi.com/api/v3/references/thesaurus/json/${this.word}?key=${key}`)
      const results = await response.json()
      results.map(result => {
        console.log(result)
        this.results.push({
          id: result.meta.id,
          speech: result.fl,
          syns: result.meta.syns[0],
          def: result.shortdef[0],
          word: result.hwi.hw
        })
      })
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
