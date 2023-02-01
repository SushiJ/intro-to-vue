<script>
export default {
  props: {
    character: Object,
    required: true,
  },
  emits: ['favorite'],
  methods: {
    favoriteCharacter() {
      this.$emit('favorite', this.character)
    }
  },

}
</script>

<template>
  <div class="text-center text-lg text-rose-100">
    <h6>{{ character.name }}</h6>
    <div class="">
      <img :src="character.image" :alt="character"
        class="object-cover h-40 w-40 rounded-sm border border-2 border-rose-400">
    </div>
    <button @click="favoriteCharacter" class="bg-zinc-500 p-2 mt-4 rounded-sm hover:bg-zinc-600">
       Favorite
    </button>
  </div>

</template>
