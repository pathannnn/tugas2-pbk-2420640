<script setup>
import { ref } from 'vue'

const titleClass = ref('title')
const count = ref(0)
const text = ref('')
const awesome = ref(true)
const isRed = ref(true)  

function increment() {
  count.value++
  toggleColor()  
}

function toggle() {
  awesome.value = !awesome.value
}

function toggleColor() {
  isRed.value = !isRed.value 
}
</script>

<template>
  <div class="container">
    <h1 :class="isRed ? 'title' : 'title-black'">HOW YOUR DAY?</h1>
    <button class="btn btn-primary" @click="increment">Count is: {{ count }}</button>
    <input v-model="text" class="input-text" placeholder="Type here">
    <p class="display-text">{{ text }}</p>
    <button class="btn btn-secondary" @click="toggle"> Reaction</button>
    <h1 v-if="awesome" class="emoji">😊 I am Happy</h1>
    <h1 v-else class="emoji">I am not sad 😢</h1>
  </div>
</template>

<style>
body {
  font-family: 'Arial', sans-serif;
  background-color: #f0f0f0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 5%;
  margin-left: 20rem;
}

.container {
  background-color: #ffffff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  text-align: center;
  width: 300px;
  margin:0;
}

.title, .title-black {
  margin-bottom: 20px;
  transition: color 0.5s;
  font-weight: bold;
}

.title {
  color: red;
}

.title-black {
  color: rgb(0, 0, 0);
}

.btn {
  margin: 10px 0;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.1s, transform 0.1s;
}

.btn-primary {
  background-color: #007bff;
  color: white;
}

.btn-primary:hover {
  background-color: #0056b3;
  transform: scale(1.05);
}

.btn-secondary {
  background-color: #6c757d;
  color: white;
}

.btn-secondary:hover {
  background-color: #5a6268;
  transform: scale(1.05);
}

.input-text {
  margin: 10px 0;
  padding: 10px;
  width: calc(100% - 20px);
  border: 1px solid #ced4da;
  border-radius: 5px;
}

.display-text {
  margin: 10px 0;
  padding: 10px;
  background-color: #e9ecef;
  border-radius: 5px;
  color: black;
}

.emoji {
  color: black;
  margin-top: 20px;
  font-size: 24px;
}
</style>
