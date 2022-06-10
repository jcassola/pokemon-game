<template>
  <div>
    <h1>Quien es este pokemon</h1>

    <pokemon-picture :pokemonId="4" :showPokemon="true"/>

    <pokemon-options :pokemons="pokemonArr" />

  </div>
</template>

<script>
import PokemonPicture from '@/components/PokemonPicture.vue'
import PokemonOptions from '@/components/PokemonOptions.vue'

import getPokemonOptions from '@/helpers/getPokemonOptions'

// console.log(getPokemonOptions());

export default {
  components: { PokemonPicture, PokemonOptions },

  data(){
    return {
      pokemonArr: []
    }
  },
  methods: {
    async mixPokemonArray(){
      this.pokemonArr = await getPokemonOptions()
      console.log(this.pokemonArr);
    }
  },
  mounted(){
    this.mixPokemonArray()
  }

}
</script>

<style>

</style>