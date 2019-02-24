<template>
  <main >
  <div v-if="showIntro">
    <img alt="dinosaur meme" id="meme" src="https://pics.me.me/gasp-inhale-pant-puff-respire-thesaurus-13615050.png"/>
  </div>
  <ul v-if="!showIntro && results.length">
    <li v-for="result in results" v-bind:key="result.id">
      <h3>{{ result.word }} <span class="speech">{{ result.speech }}</span></h3>
      <p class="def">{{ result.def }}</p>
      <div class="syns">
        <span class="list">synonyms:</span>
        <p class="syn" v-for="syn in result.syns" v-bind:key="syn" @click="$emit('change-word', syn)">
          {{ syn }},
        </p>
      </div>
    </li>
  </ul>
  <div v-if="!showIntro && !isLoading && !results.length">
    <h4>Sorry didn't find anything</h4>
  </div>
  </main>
</template>

<script>
export default {
  name: 'CardContainer',
  props: {
    results: Array,
    showIntro: Boolean,
    isLoading: Boolean
  }
}
</script>

<style scoped>
main {
  font-family: 'Special Elite', cursive;
}
.speech {
  font-size: 1.5rem;
}
h3 {
  font-size: 3rem;
  padding: 30px 0 0;
  margin: 0;
}
h4 {
  font-size: 4rem;
  padding: 30px 0 0;
  margin: 0;
  color: rgb(6, 154, 173);
}
.def {
  font-size: 1.2rem;
  width: 90%;
  margin: 15px auto;
  text-align: left;
}
.list {
  font-size: 1.2rem;
  font-weight: bold;
}
.syns {
  text-align: left;
  padding: 10px 0 30px;
  width: 90%;
  margin: 0 auto;
}
.syn {
  margin: 1px;
  display: inline;
  transition: all ease .5s;
}
.syn:hover {
  cursor: pointer;
  font-size: 1.04rem;
  color: rgb(1, 96, 109);
}
p {
  padding: 5px 0;
}
li {
  list-style-type: none;
  background: rgb(141, 141, 141);
  box-shadow: -8px 8px 10px black;
  width: 550px;
  animation: zoom-in 1s linear;
}
@keyframes zoom-in {
 0%   { 
 transform: translatey(120%); 		
 }
 100% { 
 transform: translatey(0%); 
 }
}
ul {
  display: grid;
  grid-template-columns: repeat(auto-fit, 550px);
  grid-gap: 80px 80px;
  margin: 0 auto 50px;
  justify-content: center;
  padding: 20px;
}
#meme {
  height: 420px;
  box-shadow: -8px 8px 10px black;
}

</style>