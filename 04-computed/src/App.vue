
<script setup>
import { ref, reactive, computed } from 'vue'

const count = ref(1)

const books = reactive({
  name: 'trong123',
  author: 'binhtrong',
  year: 2004,
  chapters: []
})

const addChapter = () => {
  books.chapters.push(count.value++)
}

const isPublished = computed(() => (books.chapters.length > 0 ? 'đã xuất bản' : 'chưa xuất bản'))

const firstName = ref('binh')
const lastName = ref('trong')
const fullname = computed({
  get() {
    return firstName.value + ' ' + lastName.value
  },
  set(newValue) {
    ;[firstName.value, lastName.value] = newValue.split(',')
  }
})

const changeName = () => {
  fullname.value = 'tran van,b'
}
</script>

<template>
  <!-- 
  <div>
      <h1>ok</h1>
    <div>
      <p>Tên sách : {{ books.name }}</p>
      <p>chapters : {{books.chapters}}</p>
      <p>Trạng thái xuất bản :{{isPublished}}</p>

      <button @click="addChapter">add chapter</button>
    </div>
  </div> -->

  <div>
    <p>name :{{ firstName }}</p>
    <p>name :{{ lastName }}</p>
    <p>name :{{ fullname }}</p>
    <button @click="changeName">change Fullname</button>
  </div>
</template>
