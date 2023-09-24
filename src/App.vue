<template>
  <div id="app">
    <RandomUserList />
  </div>
</template>

<script>
import RandomUserList from './components/RandomUserList.vue';

export default {
  components: {
    RandomUserList,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
</style>
