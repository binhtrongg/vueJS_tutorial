<script setup>
import { ref, reactive, computed } from 'vue'
const isActive=ref(true)
const hasError=ref(true)
const obj =computed(()=>({
  active:isActive.value,
  'has-error':hasError.value
}))
const changeClass=()=>{
  isActive.value=!isActive.value
}
</script>

<template>
  <div>
   <button class="button" :class="obj">{{isActive ? 'active' :'deactive'}}</button>

   <button class="button" :class="isActive ? 'active' :''">{{isActive ? 'active' :'deactive'}}</button>

   <button @click="changeClass">change</button>
  </div>
</template>

<style>
.button{
  border: none;
  background: rgb(179, 166, 179);
  color: azure;
  padding: 14px;
  border-radius: 3px;
  cursor: pointer;
}
.active{
  border: none;
  background: rgb(99, 36, 99);
  color: azure;
  padding: 14px;
  border-radius: 3px;
  cursor: pointer;
}

.has-error{
  background: red;
}
</style>