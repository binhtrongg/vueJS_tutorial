<script setup>
import { ref, reactive, computed } from 'vue'
const shoppingItems = ref([
  {
    name: 'apple',
    price: 7
  },
  {
    name: 'orange',
    price: 12
  },
  {
    name: 'lemon',
    price: 3
  }
])

const user = ref({
  firstName: 'john',
  lastName: 'doe',
  age: 30
})
const users = ref([
  { firstName: 'john', lastName: 'doe', age: 30,isActive:true },
  { firstName: 'binh', lastName: 'trong', age: 30 ,isActive:false},
  { firstName: 'hoang', lastName: 'hải', age: 30,isActive:true }
])
const newTodo=ref('')
const todos=ref([
  {
    id:1,
    name:'ăn'
  },
  {
    id:2,
    name:'ăn'
  }

])

const addTodo=()=>{
  if(newTodo.value.trim()===""){
    alert('vui lòng nhập')
    return
  }

  const todo={
    id:todos.value.length+1,
    name:newTodo.value
  }
  todos.value.push(todo)
  newTodo.value=''
}
</script>

<template>
  <div>
    <input type="text" v-model="newTodo">
    <button @click="addTodo" @keyup.enter="addTodo">add</button>
    <ul>
      <li v-for="todo in todos" :key="todo.id">
        {{todo.id}}.{{todo.name}}
      </li>
    </ul>
  </div>
</template>

<style></style>
