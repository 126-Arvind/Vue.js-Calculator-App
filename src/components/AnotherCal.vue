<script setup>
import {ref } from 'vue'

const display = ref("")
const add = (value) =>{
    if(display.value==="0"){
        display.value =='0'

    }
    else{
        display.value += value
    }
}

const calculation = ()=>{
    try {
    display.value = eval(display.value).toString();
  } catch (error) {
    display.value = "Error";
  }
}


const cleared = ()=>{
    display.value =''
}

const oneStepback = ()=>{

    display.value = display.value.slice(0, -1);
}
</script>

<template>
  <h1>My Calculator</h1>
  <div class="back">
    
    <input v-model="display" :class="oneStepback"  class="model" placeholder="Make your calculations easy by using me..." />
    

    <div class="buttons">
    <div>
      <button @click="add('7')" class="calculate">7</button>
      <button @click="add('8')" class="calculate">8</button>
      <button @click="add('9')" class="calculate">9</button>
      <button @click="add('/')" class="calculate">/</button>
    </div>
      <div>
      <button @click="add('4')" class="calculate">4</button>
      <button @click="add('5')" class="calculate">5</button>
      <button @click="add('6')" class="calculate">6</button>
      <button @click="add('*')" class="calculate">*</button>
      </div>
      <button @click="add('1')" class="calculate">1</button>
      <button @click="add('2')" class="calculate">2</button>
      <button @click="add('3')" class="calculate">3</button>
      <button @click="add('-')" class="calculate">-</button>
      <div>
      <button @click="add('0')" class="calculate">0</button>
      <button @click="add('.')" class="calculate">.</button>
      <button @click="calculation" class="calculate">=</button>
      <button @click="add('+')" class="calculate">+</button>
      </div>
    </div>
    <button @click="oneStepback"class="clear"><--</button>
    <button @click="cleared"class="clear">C</button>
  </div>
</template>

<style>
h1 {
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}

.model {
  margin-bottom: 20px;
  margin-left: 12px;
  padding:7px;
  min-width: 310px;
  border: 2px solid rgb(102, 243, 9);
}

.calculate {
  color: black;
  background-color: rgb(102, 243, 9);
  border-radius: 20px;
 padding-left: 30px;
 padding-right: 30px;
margin-left: 10px;
margin-bottom: 10px;
}
.calculate:hover{
background-color: rgb(54, 196, 35);
}

.clear {
  color: black;
  background-color: rgb(102, 243, 9);
  border-radius: 20px;
  margin-top: 10px;
  padding-left: 66px;
  padding-right: 66px;
  margin-left: 10px;
}
.clear:hover{
    background-color: rgb(54, 196, 35);
  
}

.back {
  background-image: url('../assets/texture-dark.jpg');
  background-size: cover; 
  background-position: center; 
  padding-top: 20px;
  padding-left: 20px;
  padding-bottom: 20px;
  padding-right: 30px;
  border: 3px solid rgb(102, 243, 9);
 
}
</style>
