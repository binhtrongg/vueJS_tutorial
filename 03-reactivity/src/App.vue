<script setup>
import { ref } from 'vue'

const count = ref(1)

count.value++

const obj = ref({
  id: 2,
  user: {
    age: 12,
    usname: 'trong'
  },
  arr: [1, 2, 3]
})

const increase = () => {
  obj.value.id++
  obj.value.arr.push(4)
}

const decrease = () => {
  if (obj.value.id === 0) {
    return
  }
  obj.value.id--
   obj.value.arr.pop()
}
</script>

<template>
  <div>
    <div>
      <p>count : {{ count }}</p>
      <button @click="count++">increase</button>
    </div>

    <div>
      <p>{{ obj.id }}</p>
      <p>{{ obj.arr }}</p>

      <button @click="increase">Tăng</button>
      <button @click="decrease">giảm</button>
    </div>
  </div>
</template>
