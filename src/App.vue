<template>
  <HelloWorld msg="Herzlich Willkommen zum Spiel Schere-Stein-Papier!"/>
  <div>Picked: {{ picked }}</div>

  <input class="rd" type="radio" id="stein" value="Stein" v-model="picked" />
  <label for="stein">Stein</label>

  <input class="rd" type="radio" id="schere" value="Schere" v-model="picked" />
  <label for="schere">Schere</label>

  <input class="rd" type="radio" id="papier" value="Papier" v-model="picked" />
  <label for="papier">Papier</label><br>
  <button @click="generateComputerChoice">Eingeben</button>

  <p id="pa">Computer chose: {{computer_choice}}</p>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<script setup> 


import { ref } from 'vue'
const picked = ref('')
const computer_choice = ref(``)
function generateComputerChoice(){
let choices = ['Stein', 'Schere', 'Papier'];
let index = Math.floor(Math.random() * 3);
computer_choice.value = choices[index]; 
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
