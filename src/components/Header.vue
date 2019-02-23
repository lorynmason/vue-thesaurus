<template>
  <header>
    <img alt="logo" src="../assets/dino.png">
    <div>
      <h1>thesaurus</h1>
      <p>the most synonymous of all the dinosaurs</p>
    </div>    
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style scoped>
header {
  font-family: 'Special Elite', cursive;
  display: flex;
  justify-content: center;
  align-items: flex-end;
}
h1 {
  margin: 0;
  font-size: 5rem;
}
p {
  margin: 0;
  font-size: 1.5rem;
}
img {
  margin: 10px 0 0 -20px;
  filter: invert(50%) drop-shadow(-4px 2px black);
}
</style>