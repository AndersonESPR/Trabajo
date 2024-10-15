<template>
  <div class="counter-container">
    <h1 class="counter-title">ESTE ES EL COUNTER DOS</h1>
    <h1 class="counter-value">{{ counter }}</h1>
    <button class="counter-btn increment-btn" @click="increment">+1</button>
    <button class="counter-btn decrement-btn" @click="decrement">-1</button>
    <button class="counter-btn increment-by-btn" @click="incrementBy(5)">+5</button>
  </div>
</template>

<script setup>
const props = defineProps({
  counter: {
    type: Number,
    required: true
  }
});

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

<style scoped>
.counter-container {
  margin: 20px;
  text-align: center;
}

.counter-title {
  font-size: 1.5rem;
  color: #007acc;
}

.counter-value {
  font-size: 2rem;
  color: #004080;
  margin: 10px 0;
}

.counter-btn {
  background-color: #007acc;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 1rem;
  margin: 5px;
  cursor: pointer;
  border-radius: 5px;
  transition: background-color 0.3s;
}

.counter-btn:hover {
  background-color: #005b99;
}

.increment-btn {
  background-color: #28a745;
}

.decrement-btn {
  background-color: #dc3545;
}

.increment-by-btn {
  background-color: #ffc107;
}
</style>
