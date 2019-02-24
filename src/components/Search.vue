<template>
   <div class="search">
      <input placeholder="find synonyms" v-model="word"/> 
      <button @click="$emit('change-word', word)">SEARCH</button> 
    </div>
</template>

<script>
export default {
  name: 'Search',
   data(){
    return {
      word: ''
    }
  },
}
</script>

<style scoped>
.search {
  margin: 50px auto;
}
input, button {
  margin: 0 15px;
  font-family: 'Special Elite', cursive;
  font-size: 1.2rem;
  height: 40px;
  border: none;
  outline: none;
}

button {
  font-family: 'Special Elite', cursive;
  background: rgb(145, 145, 145);
  border-radius: 5px;
  box-shadow: -8px 8px 10px black;
  cursor: pointer;
  transition: all ease .5s;
  padding-top: 6px;
}
button:hover {
  transform: scale(1.06);
  background: rgb(1, 96, 109);
}
</style>