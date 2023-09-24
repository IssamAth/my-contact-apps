<template>
  <nav class="bg-blue-500 p-4 h-16">
    <div class="mx-auto flex justify-between items-center">
      <div class="text-white font-semibold text-lg">My Contacts App</div>
    </div>
  </nav>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const isOpen = ref(false);

    const toggleMenu = () => {
      isOpen.value = !isOpen.value;
    };

    return {
      isOpen,
      toggleMenu,
    };
  },
};
</script>

<style scoped>
/* Add any scoped styles here */
</style>
