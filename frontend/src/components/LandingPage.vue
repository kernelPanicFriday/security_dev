<template>
   <div class="container mx-auto bg-gray-200 rounded-xl shadow border p-8 m-10">
     <p class="text-3xl text-gray-700 font-bold mb-5">
       Welcome!
     </p>
     <p class="text-gray-500 text-lg">
       My name is Ty Brown and I'm a Full Stack Developer for the Intercontinel Exchange's Cybersecurity department.
     </p>
  </div>
</template>

<script setup>
import { onMounted, reactive } from 'vue'; 

let msg = reactive([])

async function update(){
  console.log('fetching')
  fetch("http://localhost:8000/test")
    .then((response => {
      return response.json()
  })).then((data => {
    msg.push(data)
  }))
}

onMounted(() => update());
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
