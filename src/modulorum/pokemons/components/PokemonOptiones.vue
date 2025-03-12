<template>
  <section class="flex flex-col mt-5">
    <button
    @click= "$emit('electusOptio', id)"
    v-for="{nomen, id} in optiones"
    :key="id"
    class="capitalize"
    >
      {{nomen}}
  </button>
  </section>
  
</template>

<script setup lang="ts">
import type { Pokemon } from '../interfaces';

interface Props {
  optiones: Pokemon[];
}
defineProps<Props>();
defineEmits<{
  electusOptio: [id: number];
}>();

</script>

<style scoped>
@import 'tailwindcss';

button {
  @apply bg-white shadow-md rounded-lg cursor-pointer w-40 p-3 my-2 text-center hover:bg-gray-100 transition-all;
}
</style>
