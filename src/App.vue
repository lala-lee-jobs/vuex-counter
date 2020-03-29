<template>
  <div>
    <h1>{{count}}</h1>
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
    ...mapState(['count', 'username', 'list']),
    myCount() {
      return this.localCount;
    }
  },
  methods: {
    ...mapMutations(['increment']),
  }
}
</script>