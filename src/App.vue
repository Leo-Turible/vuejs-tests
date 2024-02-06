<script setup>
import Notes from "@/components/Notes.vue";
import Boucles from "@/components/Boucles.vue";
import {computed} from "vue";

const title = 'Notes'
const paragraphe = 'Voici mes notes'

//fait un tableau avec des mots
const words = ['un', 'deux', 'trois']
const matières = ['Symfony', 'Intégration', 'Réseau', 'Mathématiques', 'Anglais']
const listeMatieres = computed(() => {
  return matières.join(', ')
})
</script>

<template>
  <header>
  </header>

  <main>
    <h1>{{ title }}</h1>
    <p>{{ paragraphe }}</p>

    <Notes />
    <ul>
      <li v-for="word in words" :key="word">{{ word }}</li>
    </ul>
    <p>Les matières sont : {{ listeMatieres }}</p>

    <Boucles />



  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}

li {
  color: #767676;
}
</style>
