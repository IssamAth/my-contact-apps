<template>
  <div class="container mx-auto">
    <!-- PERSON -->
    <div class="flex flex-wrap justify-center lg:max-w-screen-xl">
      <div
        v-for="(person, index) in people"
        :key="index"
        class="w-1/4 sm:w-1/3 md:w-1/4 lg:w-1/6 mx-2 my-2 shadow-lg rounded-md hover:shadow-2xl drop-shadow-lg"
      >
        <img
          class="h-32 rounded-t-xl"
          :src="person.picture.large"
          :alt="`${person.name.first} ${person.name.last}`"
        />
        <div class="h-32 p-3 flex flex-col">
          <h2>{{ `${person.name.first} ${person.name.last}` }}</h2>
          <p class="whitespace-normal h-full break-all">{{ person.email }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const people = ref([]);

onMounted(() => {
  // Fetch multiple users (for example, 5 users) from the API
  fetch('https://randomuser.me/api/?results=100')
    .then(response => {
      if (!response.ok) {
        throw new Error('Network response was not ok');
      }
      return response.json();
    })
    .then(data => {
      people.value = data.results;
    })
    .catch(error => {
      console.error('Fetch error:', error);
    });
});
</script>
