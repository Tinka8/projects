<template>
  <main>
    <div class="relative h-64 w-64 left-1/3 py-10">
      <div class="bg-blue-100 rounded text-center p-6">
        <h4 class="text-lg font-semibold">
          The current count is...
        </h4>
        <h1 class="p-2 text-3xl font-semibold">{{ count }}</h1>
        <button @click="count--" class="border border-1 border-gray-200 shadow-xl rounded-lg bg-white px-6 m-4">-</button>
        <button @click="count++" class="border border-1 border-gray-200 shadow-xl rounded-lg bg-white px-6 m-4">+</button>
      </div>
    </div>
  </main>
</template>



<script setup>
  import { ref } from "vue";

  const count = ref(0);


  
</script>
