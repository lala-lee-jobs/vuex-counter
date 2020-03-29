<template>
  <div>
    <h1>{{count}}</h1>
    <button @click="addCount">Add</button>
  </div>
</template>

<script>
import store from './store';

export default {
  computed: {
    count() {
      return store.state.count;
    }
  },
  methods: {
    addCount() {
      store.commit('increment');
    }
  },
}
</script>