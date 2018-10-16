<template>
  <div class="counter-warp">
    <p>Vuex counter：{{ count }}</p>
    <p>
      <button @click="onCount(1)">+</button>
      <button @click="onCount(-1)">-</button>
    </p>

    <a href="/pages/index/main" class="home">去往首页</a>
  </div>
</template>

<script>
// Use Vuex
// import store from './store'
import { mapState } from 'vuex'

export default {
  computed: {
    ...mapState(['count'])
  },
  methods: {
    onCount (count) {
      const counted = this.count + count
      this.$store.commit('count', counted)
    }
  }
}
</script>

<style>
.counter-warp {
  text-align: center;
  margin-top: 100px;
}
.home {
  display: inline-block;
  margin: 100px auto;
  padding: 5px 10px;
  color: blue;
  border: 1px solid blue;
}
</style>
