<template>
  <main>
    {{ results }}
  </main>
</template>

<script>
export default {
  name: 'CardContainer',
   created() {
    this.$emit('created');
  },
  props: {
    results: Array
  }
}
</script>

<style scoped>

</style>