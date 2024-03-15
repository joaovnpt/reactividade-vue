<script setup>
  import { computed, ref } from 'vue';

  const contador1 = ref(0);
  const contador2 = ref(0);
  const valorBooleano = ref(true);

  function incrementar(contador) {
    eval(contador).value++;
  }

  function decrementar(contador) {
    if (eval(contador).value > 0) {
      eval(contador).value--;
    }
  }

  const soma = computed(() => contador1.value + contador2.value);
  const somaPar = computed(() => soma.value % 2 === 0);
  const somaMaiorQue10 = computed(() => soma.value > 10);
</script>

<template>
  <h1>Correção dos exercícios</h1>
  <div class="booleano">
    <button @click="valorBooleano = !valorBooleano">
       {{ valorBooleano ? 'Esconder Resultado' : 'Mostrar Resultado' }}
      
    </button>
  </div>
  <div v-if="valorBooleano">
    <div class="contador">
      <h2>Contador 1</h2>
      <button @click="incrementar('contador1')">Incrementar</button>
      <button @click="decrementar('contador1')">Decrementar</button>
      <p>Valor: {{ contador1 }}</p>
    </div>
    <div class="contador">
      <h2>Contador 2</h2>
      <button @click="incrementar('contador2')">Incrementar</button>
      <button @click="decrementar('contador2')">Decrementar</button>
      <p>Valor: {{ contador2 }}</p>
    </div>
    <div class="soma">
      <h2>Soma</h2>
      <p>Valor:  {{ soma }} </p>
      <div v-if="somaMaiorQue10">
        <p>A soma é maior que 10</p>
      </div>
      <div v-else>
        <p>A soma é menor que 10</p>
      </div>
      <div v-if="somaPar">
        <p>A soma é par</p>
      </div>
      <div v-else>
        <p>A soma é ímpar</p>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>


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
