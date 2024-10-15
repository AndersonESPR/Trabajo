<template>
  <div class="app-container">
    <h1 class="app-title">PARCIAL DOS</h1>
    <hr class="divider" />
    <CounterUno :counter="counter1" @updateCounter="counter1 = $event" />
    <CounterDos :counter="counter2" @updateCounter="counter2 = $event" />
    <CounterCopy3 :counter="counter3" @updateCounter="counter3 = $event" />
    <hr class="divider" />
  </div>
</template>

<script setup>
import CounterDos from './components/CounterDos.vue'
import useCounter from './composable/UseCounter.js'
import CounterUno from './components/CounterUno.vue'
import CounterCopy3 from './components/MyCounter3.vue'

const { counter: counter1 } = useCounter(1);
const { counter: counter2 } = useCounter(2);
const { counter: counter3 } = useCounter(3);
</script>

<style scoped>
.app-container {
  text-align: center;
  padding: 20px;
  background-color: #f0f8ff; /* Azul muy claro */
}

.app-title {
  font-size: 3rem;
  color: #007acc; /* Azul vivo */
  text-shadow: 2px 2px #004080; /* Sombra de texto */
}

.divider {
  margin: 20px 0;
  border: none;
  height: 2px;
  background-color: #007acc;
}

.divider-line {
  font-size: 1rem;
  color: #007acc;
}
</style>
