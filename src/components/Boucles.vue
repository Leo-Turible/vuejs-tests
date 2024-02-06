<script setup>
import { ref } from 'vue'

const awesome = ref(true)

const toggleAwesome = () => {
  awesome.value = !awesome.value
}

const notes = ref([7, 9, 11, 13, 15, 18, 20, 10, 12, 14])
</script>

<template>
  <button @click="toggleAwesome">Basculer</button>

  <div v-if="awesome">
    <h1 >Vue est magnifique!</h1>
    <ul>
      <li v-for="(note, index) in notes" :key="index" :class="note > 10 ? 'green' : 'red'">
        Note {{ index + 1 }} : {{ note }} -
        <span v-if="note > 10">Supérieure à 10 </span>
        <span v-else-if="note >= 8 && note <= 10">Entre 8 et 10 </span>
        <span v-else">Inférieure à 8</span>
      </li>
    </ul>
  </div>

  <div v-else>
    <h1>Oh non 😢</h1>
  </div>


</template>

<style scoped>
.green {
  color: green;
}

.red {
  color: red;
}
</style>