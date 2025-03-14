<template>
  <section v-if="estPortat || temerePokemon.id ==null" class="flex flex-col items-center justify-center h-screen w-screen">
    <h1 class="text-3xl">Espere,porfavor</h1>
    <h3 class="animate-pulse">Cargando Pokèmons</h3>
  </section>

  <section v-else class="flex flex-col items-center justify-center h-screen w-screen">
    
    <h1 class="m-5">¿Quién es este Pokèmon?</h1>
    
    <!-- <h3>{{temerePokemon.nomen }}</h3> -->
    
    <h3 class="catipatalize my-3">{{ ludumStatus }}</h3>

     <div class="h-20">
      <button
      v-if="ludumStatus!==LudumStatus.Ludit"
      @click="sequentiOptiones(4)"
      class="bg-blue-500 text-white px-4 p-2.5 rounded-lg hover:bg-blue-700 transition-all">
        Jugar de nuevo?
      </button>
     </div>
    <PokemonImago :pokemon-id="temerePokemon.id" :revelarePokemon="ludumStatus !== LudumStatus.Ludit"/>
    <PokemonOptiones 
    :optiones="optiones"
    @electus-optio="examineResponsio"
    :non-eligere="ludumStatus !== LudumStatus.Ludit"
    :recte-responsio="temerePokemon.id"
    />

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
  sequentiOptiones,
} = usePokemonLudum();

// const cumElectusOptio = (valorem: number) =>{
//   console.log({valorem});
  
// }

</script>

<style scoped>

</style>
