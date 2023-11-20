<template>
  <div class="hello">
    <h2>ayoooo</h2>
    <h1>{{ msg }}</h1>
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
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
