<template>
  <header>
    <img alt="logo" src="../assets/dino.png">
    <div class="title">
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
  margin: 20px auto 0;
  animation: pulse 5s infinite;
  color: rgb(1, 96, 109);
}
.title {
  margin-left: -100px;
  text-shadow: -8px 4px 2px black;
}
@keyframes pulse {
  50% {
    transform: scale(1.08);
    color: rgb(6, 154, 173);
  }
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
  filter: invert(90%) drop-shadow(-8px 4px 2px black);
}
</style>