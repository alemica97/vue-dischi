<template>
  <div id="app">
    <myHeader />

    <myMain />
    
  </div>
</template>

<script>
import myHeader from './components/Header.vue'
import myMain from './components/Main.vue'

export default {
  name: 'App',
  components: {
    myHeader,
    myMain,
  }
}
</script>

<style lang="scss">
@import './assets/scss/common.scss';

#app {
  font-family: "Cooper Hewitt", sans-serif;
  -webkit-font-smoothing: antialiased;
}
</style>
