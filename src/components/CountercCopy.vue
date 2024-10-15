<template>
    <h1>ESTE ES EL COUNTER e</h1>
  
    <!-- Mostrando el valor pasado por prop -->
    <h1>{{ counter }}</h1>
    <button @click="increment">+1</button>
    <button @click="decrement">-1</button>
    <button @click="incrementBy(5)">+5</button>
  </template>
  
  <script setup>
  // Recibe counter como prop desde App.vue
  const props = defineProps({
    counter: {
      type: Number,
      required: true
    }
  });
  
  // Emitimos el evento para actualizar el counter en App.vue
  const emit = defineEmits(['updateCounter']);
  
  const increment = () => {
    emit('updateCounter', props.counter + 1);
  };
  
  const decrement = () => {
    emit('updateCounter', props.counter - 1);
  };
  
  const incrementBy = (value) => {
    emit('updateCounter', props.counter + value);
  };
  </script>
  
