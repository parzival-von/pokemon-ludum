<template>
  <section v-if="estPortat || temerePokemon.id ==null" class="flex flex-col items-center justify-center h-screen w-screen">
    <h1 class="text-3xl">Espere,porfavor</h1>
    <h3 class="animate-pulse">Cargando Pokèmons</h3>
  </section>

  <section v-else class="flex flex-col items-center justify-center h-screen w-screen">
    <h1 class="m-5">¿Quién es este Pokèmon?</h1>
    <h3>{{temerePokemon.nomen }}</h3>
     <h3 class="catipatalize my-3">{{ ludumStatus }}</h3>
    <PokemonImago :pokemon-id="temerePokemon.id" :revelarePokemon="ludumStatus !== LudumStatus.Ludit"/>
    <PokemonOptiones :optiones="optiones" @electus-optio="examineResponsio"/>
  </section>
</template>

<script setup lang="ts">
import PokemonImago from '../components/PokemonImago.vue';
import PokemonOptiones from '../components/PokemonOptiones.vue';
import { usePokemonLudum } from '../composables/usePokemonLudum.ts';
import { LudumStatus } from '../interfaces/ludum-status.enum.ts';

const {
  ludumStatus,
  estPortat,
  temerePokemon,
  pokemonOptiones : optiones,
  examineResponsio,
} = usePokemonLudum();

// const cumElectusOptio = (valorem: number) =>{
//   console.log({valorem});
  
// }

</script>

<style scoped></style>
