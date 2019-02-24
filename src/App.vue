<template>
  <div id="app">
    <Header />
    <Search @change-word="word=($event), search()"/>
    <CardContainer :results="results" @change-word="word=($event), search()"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import { key } from './apikey.js'
import CardContainer from './components/CardContainer.vue'
import Search from './components/Search.vue'

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
    CardContainer,
    Search
  },
  methods: {
    async search(){
      this.results = []
      const response = await fetch(`https://www.dictionaryapi.com/api/v3/references/thesaurus/json/${this.word}?key=${key}`)
      if(response.ok){
        const results = await response.json()
        results.map(result => {
          this.results.push({
            id: result.meta.id,
            speech: result.fl,
            syns: result.meta.syns[0],
            def: result.shortdef[0],
            word: result.hwi.hw
          })
        })
      } else {
        console.log('error')
      }
    }
  }
}
</script>

<style>
body {
  text-align: center;
  color: #000000;
  background: #202020;
  margin: 0;
  width: 100vw;
  overflow-x: hidden;
}
</style>
