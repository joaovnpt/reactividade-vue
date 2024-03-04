<script setup>
 import { ref } from 'vue';

const contador = ref(0);

function add() {
  contador.value++;
}

function minus() {
  contador.value--;
}

function reset() {
  contador.value = 0;
}

</script>

<template>
<div class="contador1">
  <button @click="add()">+</button>
  <p>{{ contador }}</p>
  <button @click="minus()">-</button>
  <button @click="reset()">C</button>
</div>
<div class="contador2">
  <button @click="add()">+</button>
  <p>{{ contador }}</p>
  <button @click="add()">-</button>
  <button @click="add()">C</button>
</div>
<div class="quadro-soma"></div>
</template>

<style scoped>
.contador1 {
  background-color: black;
  padding: 25px;
  display: flex;
  justify-content: center;
  align-items: center;
}
p {
  font-size: larger;
  color: white;
  margin-right: 5px;
  margin-left: 5px;
}
button {
  margin-left: 5px;
  margin-right: 5px;
}

.contador2 {
  background-color: rgb(255, 0, 0);
  padding: 25px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
