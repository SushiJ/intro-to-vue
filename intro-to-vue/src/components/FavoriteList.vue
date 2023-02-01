<script>
export default {
  props: {
    favoriteCharacter: Object,
    required: true,
  },
  emits: ['removeFavorite'],
  methods: {
    removeCharacter() {
      this.$emit("removeFavorite", this.favoriteCharacter)
    }
  }
}
</script>

<template>
  <button @click="removeCharacter" class="bg-zinc-500 p-2 rounded-sm m-1 hover:bg-red-400">
    {{ favoriteCharacter.name }}
  </button>
</template>
