<template>
  <main>
  <ul>
    <li v-for="result in results" v-bind:key="result.id">
      <h3>{{ result.word }}</h3>
      <p>{{ result.speech }}</p>
      <p>{{ result.def }}</p>
      syns: 
      <p class="syn" v-for="syn in result.syns" v-bind:key="syn" @click="$emit('change-word', syn)">
        {{ syn }},
      </p>
    </li>
  </ul>
  </main>
</template>

<script>
export default {
  name: 'CardContainer',
  props: {
    results: Array
  },
  data() {
    return {
      word: ''
    }
  }
}
</script>

<style scoped>

.syn {
  display: inline;
}

li {
  list-style-type: none;
  background: rgb(141, 141, 141);
  margin: 0 auto;
}

ul {
  margin: 0 auto;
  width: 500px;
}

</style>