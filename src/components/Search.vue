<template>
  <div>
    <input placeholder="find synonyms"/> 
    <button>SEARCH</button> 
  </div>
</template>

<script>
export default {
  name: 'Search',
   created() {
    this.$emit('created');
  }
}
</script>

<style scoped>
div {
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