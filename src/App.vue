<script setup>
import { ref, computed } from 'vue'

const contador = ref(0)
const contador2 = ref(0)
const somaMaiorQue10 = computed(() => {
  return contador.value + contador2.value > 10;
});

function add() {
  contador.value++
}

function minus() {
  contador.value--
}

function reset() {
  contador.value = 0
}

function add2() {
  contador2.value++
}

function minus2() {
  contador2.value--
}

function reset2() {
  contador2.value = 0
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
    <button @click="add2()">+</button>
    <p>{{ contador2 }}</p>
    <button @click="minus2()">-</button>
    <button @click="reset2()">C</button>
  </div>
  <div class="quadro-soma">
    <p>A soma dos contadores é:</p>
    {{ contador + contador2 }}
    <hr />
    <div v-if="somaMaiorQue10" class="menor-dez">
      <span>Soma maior que 10!</span></div>
    <div v-else-if="contador + contador2 == 10">Soma igual a 10</div>
    <div v-else><span>Soma menor que 10</span></div>
  </div>
  <div class="par-impar">
    <p>A soma dos contadores é:</p>
    <div v-if="(contador + contador2) % 2 == 0"><span>Par</span></div>
    <div v-else>Ímpar</div>
  </div>
</template>

<style scoped>
.contador1 {
  background-color: #048c73;
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
  background-color: #d9b504;
  padding: 25px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.quadro-soma {
  background-color: #b666d9;
  padding: 25px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.par-impar {
  background-color: #3d32dd;
  padding: 25px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-size: large;
}
span {
  color: white;
}
</style>
