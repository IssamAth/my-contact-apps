<template>
  <div class="container mx-auto">
    <!-- PERSON -->
    <div class="container mx-auto flex flex-wrap justify-center">
      <div
        v-for="(person, index) in people"
        :key="index"
        class="flex flex-col   mx-2 mb-8 shadow-lg rounded-md md:h-30v h-50 hover:shadow-2xl drop-shadow-lg w-full sm:w-1/2 md:w-1/3 lg:w-1/4 xl:w-1/6 flex-grow hover:cursor-pointer"
      >
        <img
          class="h-48 rounded-t-xl"
          :src="person.picture.large"
          :alt="`${person.name.first} ${person.name.last}`"
        />
        <div class=" h-full space-y-3 p-3 flex flex-col justify-center">
          <h2 class="font-bold text-lg">{{ `${person.name.first} ${person.name.last}` }}</h2>
          <p class="whitespace-normal h-full break-all text-sm text-gray-500">{{ person.email }}</p>
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
