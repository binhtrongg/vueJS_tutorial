
<template>
  <div>
    <p>count:{{ count }}</p>
  </div>
</template>

<script setup>
const message = 'hello world!!'
let rawHtml = ' <span style="color: red">This should be red.</span>'
const buttonId = 'button-id'
const buttonClass = 'btn'
const isButtonDisable = false
let listString = 'a,b,c,d,e,f'
const convertToId= (data)=>data.split(',').reverse().join('-')

const objectOfAttrs = {
  id: 'container',
  class: 'wrapper',
  style: 'background-color:green'
}
const number = 0
</script>

<template>
  <div>
    <h1>Syntax</h1>
    <p>message :{{ message }}</p>
    <p>Using text interpolation: {{ rawHtml }}</p>
    <p>Using v-html directive: <span v-html="rawHtml"></span></p>
    <button :disabled="isButtonDisable">{{ isButtonDisable ? 'disable' : 'click here' }}</button>
    <button v-bind="objectOfAttrs">click here !!!</button>

    <button :id="convertToId(listString)">number : {{ number + 1 }}</button>
  </div>
</template>

