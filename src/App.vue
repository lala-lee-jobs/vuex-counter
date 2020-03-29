<template>
  <div>
    <h1>{{storeCount}}</h1>
    <button @click="add(10)">Add</button>
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
    ...mapMutations({
      'add': 'increment'
    })
  }
}
</script>