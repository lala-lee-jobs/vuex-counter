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

      // 使用函式的方式存取state
      storeCount(state) {
        return state.count;
      },

      // 上述的方式，可改寫成 arrow function，更簡潔
      storeCount: state => state.count,
      
      // 也可以使用字串的方式，取得在state中的定義好的property
      // 等同於 state => state.count
      storeCount: 'count',
      
      // 如果需要利用到 this，就要使用一般寫function的方式
      totalCount(state) {
        return this.localCount + state.count;
      }
    }),
    myCount() {
      return this.localCount;
    }
  },
  methods: {
    ...mapMutations(['increment']),
  }
}
</script>