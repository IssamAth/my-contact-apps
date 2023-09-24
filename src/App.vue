<template>
  <div class="relative flex flex-col">
    <div class="top-0 fixed left-0 w-screen z-10 mb-6">
      <Navbar />
    </div>

    <div class="mt-20 flex w-screen justify-between items-center container mx-auto h-14">
      <div class="text-4xl">
        100 Contact(s)
      </div>
      <div class="w-40v h-full">
        <SearchField />
      </div>
    </div>

    <div class="my-10 mt-4">
      <RandomUserList />
    </div>
  </div>
</template>

<script>
import RandomUserList from './components/RandomUserList.vue';
import Navbar from './components/Navbar.vue';
import SearchField from './components/SearchField.vue';

export default {
  components: {
    Navbar,
    SearchField,
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
