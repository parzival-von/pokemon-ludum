<template>
  <section v-if="estPortat" class="flex flex-col items-center justify-center h-screen w-screen">
    <h1 class="text-3xl">Espere,porfavor</h1>
    <h3 class="animate-pulse">Cargando Pokèmons</h3>
  </section>

  <section v-else class="flex flex-col items-center justify-center h-screen w-screen">
    <h1 class="m-5">¿Quién es este Pokèmon?</h1>
    <PokemonImago/>
    <PokemonOptiones/>
  </section>
</template>

<script setup lang="ts">
import PokemonImago from '../components/PokemonImago.vue';
import PokemonOptiones from '../components/PokemonOptiones.vue';
import { usePokemonLudum } from '../composables/usePokemonLudum';

const {  estPortat} = usePokemonLudum();

</script>

<style scoped></style>
