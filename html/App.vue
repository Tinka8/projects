<template>
  <main>
    <div v-if="showModal" class="overlay absolute top-0 right-0 m-32 p-8 w-auto bg-purple-300 rounded-lg">
      <div class="modal">
        <textarea v-model="newNote" name="note" id="note" cols="40" rows="10" class="bg-gray-100 rounded"></textarea>
        <button @click="addNote" class="bg-blue-100 m-4 p-2 rounded pointer-events-auto">Add Note</button>
        <button @click="showModal = false" class="bg-blue-100 m-4 p-2 px-4 rounded pointer-events-auto">Close</button>
      </div>
    </div>
    <div class="w-auto bg-purple-200 p-4 m-10 rounded-lg">
      <header class="flex justify-between">
        <h1 class="font-bold text-4xl">Notes</h1>
        <button @click="showModal = true" class="border-2 border-stone-200 rounded-xl bg-stone-100 px-6 p-2">+</button>
      </header>
      <div class="flex space-x-6">
        <div class="w-1/6 h-1/2 bg-yellow-400 p-4 rounded-lg mt-12">
          <p class="main-text">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Expedita laborum, quam adipisci aut accusamus nihil, animi optio maiores atque corrupti harum? Hic, vero natus culpa tenetur id reprehenderit dolorum eos!</p>
          <p class="pt-10 font-semibold">04/27</p>
        </div>
        <div class="w-1/6 h-1/2 bg-yellow-400 p-4 rounded-lg mt-12">
            <p class="main-text">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Expedita laborum, quam adipisci aut accusamus nihil, animi optio maiores atque corrupti harum? Hic, vero natus culpa tenetur id reprehenderit dolorum eos!</p>
            <p class="pt-10 font-semibold">04/27</p>
          </div>
      </div>
    </div>
  </main>
</template>



<script setup>
  import { ref } from "vue";

  const showModal = ref(false)
  const newNote = ref("")
  const notes = ref([])


  function getRandomColor() {
    return "hsl(" + Math.random() * 360 + ", 100%, 75%)"
  }




  const addNote = () => {
    notes.value.push({
      id: Math.floor(Math.random() * 1000000),
      text: newNote.value,
      date: new Date(),
      backgroundColor: getRandomColor()
    }),
    showModal.value = false
    newNote.value = ""
  }


  
</script>
