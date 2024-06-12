<script setup>
import { ref, reactive, computed } from 'vue'
const isLoggedin = ref(false)
const userStatus=ref('online');
const isVisible=ref(true)
const visibleItem=()=>{
  isVisible.value=!isVisible.value
}
const change = () => {
  isLoggedin.value = !isLoggedin.value
}
const changeStatus=()=>{
  if(userStatus.value==='online'){
    userStatus.value='away'
  }
  else if(userStatus.value==='away'){
    userStatus.value='busy'
  }else if(userStatus.value==='busy'){
    userStatus.value='online'
  }
}
</script>

<template>
  <div>
    <button @click="change">{{ !isLoggedin ? 'đăng nhập' : 'đăng xuất' }}</button>
    <h1 v-if="isLoggedin">chào mừng người dùng đăng nhập</h1>
    <h1>chào mừng user</h1>
    <h1>chào mừng assmin</h1>

    <br>
    <h1 v-if="userStatus==='online'">người dùng đang onlne</h1>
    <h1 v-else-if="userStatus==='away'">người dùng đang vắng mặt</h1>
    <h1 v-else-if="userStatus==='busy'">người dùng đang bận</h1>
    <h1 v-else>không rõ</h1>
    <button @click="changeStatus">thay đổi trạng thái</button>
    <br>
    <h1 v-show="isVisible">nội dung này ẩn hoặc hiển thị</h1>
    <button @click="visibleItem">{{isVisible?'ẩn':'hiện'}}</button>
  </div>
</template>

<style></style>
