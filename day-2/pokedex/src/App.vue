<script setup>
import PokedexWrapper from './components/PokedexWrapper.vue';
</script>
<template>
  <Suspense>
    <PokedexWrapper />
    <template v-slot:fallback>
      Loading...
    </template>
  </Suspense>
</template>

