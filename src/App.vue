<template>
  <div>
    <h1>{{count}}</h1>
    <button @click="addCount">Add</button>
  </div>
</template>
<script>
export default {
  computed: {
    count() {
      return this.$store.state.count;
    }
  },
  methods: {
    addCount() {
      this.$store.commit('increment');
    }
  },
}
</script>
<style lang="scss">
  
</style>