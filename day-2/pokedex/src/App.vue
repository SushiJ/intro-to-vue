<script>
export default {
  data: () => ({
    pokedex: [1, 2, 3]
  }),
  methods: {
    async fetchPokemon() {
      this.pokedex = await fetch("https://pokeapi.co/api/v2/pokemon?limit=100").then((res) => res.json())
    }
  }
}
</script>

<template>
  <pre>{{ pokedex }}</pre>
  <button @click="fetchPokemon">Fetch</button>
</template>

