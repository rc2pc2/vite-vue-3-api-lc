<template lang="">
  <AppHeader/>
  <main>
    <AppSearch/>
    <CharactersList :charactersList="characters"/>
  </main>
</template>

<script>
import { store } from './js/store.js';
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import CharactersList from './components/CharactersList.vue';
import AppSearch from './components/AppSearch.vue';

export default {
  components:{
    AppHeader,
    CharactersList,
    AppSearch
  },

  data() {
    return {
      characters: [],
      store
    }
  },
  methods: {
    getCharacters(){
      axios.get('https://rickandmortyapi.com/api/character')
      .then((response) => {
        // handle success
        console.log(response);
        this.store.charactersList = response.data.results;
      })
      .catch(function (error) {
        // handle error
        console.error(error);
      });
    }
  },
  created() {
    this.getCharacters();
  },
}
</script>

<style lang="scss">
  @use './styles/general.scss';

</style>