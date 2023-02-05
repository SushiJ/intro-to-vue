<script setup>
import { reactive } from 'vue';
import PokeCard from "./PokeCard.vue"
const state = reactive({
  pokedex: []
})
async function fetchPoke() {
  const res = await fetch("https://pokeapi.co/api/v2/pokemon?limit=20").then(r => r.json())
  console.log(res.results)
  return res.results
}
state.pokedex = await fetchPoke()
</script>
<template>
  <PokeCard v-for="Pokemon in state.pokedex" :Pokemon="Pokemon" />
</template>
