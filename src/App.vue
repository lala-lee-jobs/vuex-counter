<template>
  <div>
    <h1>{{storeCount}}</h1>
    <button @click="increment">Add</button>
  </div>
</template>

<script>
import { mapState, mapMutations } from 'vuex';

export default {
  data() {
    return {
      localCount: 0,
    }
  },
  computed: {
    ...mapState({
      storeCount: 'count'
    }),
    myCount() {
      return this.localCount;
    }
  },
  methods: {
    increment() {
      this.$store.commit('increment', 2);
    }
  }
}
</script>