<template lang="pug">
  #app
    .box.has-text-centered
      .columns
        .column
          p.notification.is-size-3 {{ count }}
        .column
          button.button.is-info(@click="increment")
            span.icon
              i.far.fa-plus-square.fa-2x
          button.button.is-danger(@click="decrement")
            span.icon
              i.far.fa-minus-square.fa-2x
</template>

<script>
import Vue from 'vue';
import store from './store.js';
export default {
  name: 'App',
  data: () => ({
    privateState: {}
  }),
  computed: {
    count () {
      return store.state.count
    }
  },
  methods: {
    increment () {
      store.commit('increment')
    },
    decrement () {
      store.commit('decrement')
    }
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
