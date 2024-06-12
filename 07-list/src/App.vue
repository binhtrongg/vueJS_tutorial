<script setup>
import { ref, reactive, computed } from 'vue'
const count = ref(0)
const greet = (event) => {
  console.log(event.target), alert(`xin chào ${event.type}`)
}

const sayhi=(name)=>{
  alert(`xin chào ${name}`)
}
</script>

<template>
  <div>
    <h1>event handling</h1>
    <button @click="count++">thêm 1</button>
    <p>{{ count }}</p>
    <button @click="greet">greet</button>
    <button @click="sayhi('binh')">hi</button>
    <button @click="sayhi('trong')">hi</button>
  </div>
</template>

<style></style>
