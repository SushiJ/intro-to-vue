<script setup>
import { defineProps } from 'vue';

defineProps(
  {
    Pokemon: Object,
    required: true,
  }
)
</script>

<template>
  <ul>
    <li>
      <div>
        <a :href="Pokemon.url">
          {{ Pokemon.name }}
        </a>
      </div>
    </li>
  </ul>
</template>
