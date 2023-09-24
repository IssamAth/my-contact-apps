<template>
  <div id="app">
    <Navbar />
    <RandomUserList />
  </div>
</template>

<script>
import RandomUserList from './components/RandomUserList.vue';
import Navbar from './components/Navbar.vue';

export default {
  components: {
    Navbar,
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
