<template>
  <div>
    <!-- <h3>当前最新的count值为：{{$store.state.count}}</h3> -->
    <h3>{{$store.getters.showNum}}</h3>
    <button @click="btnHandler1">+1</button>
    <button @click="btnHandler2">+N</button>
    <button @click="btnHandler3">+1 Async</button>
    <button @click="btnHandler4">+N Async</button>
  </div>
</template>

<script>
export default {
  data () {
    return {}
  },
  methods: {
    btnHandler1 () {
      this.$store.commit('add')
    },
    btnHandler2 () {
      // commit的作用，就是调用某个mutation函数
      this.$store.commit('addN', 3)
    },
    btnHandler3 () {
      // 异步的让count+1
      this.$store.dispatch('addAsync')
    },
    btnHandler4 () {
      // 异步的让count+1
      this.$store.dispatch('addNAsync', 5)
    }
  }
}
</script>
