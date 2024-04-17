<script>
import axios from 'axios';
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import CardSearcher from './components/CardSearcher.vue';

export default {
  components: {
    AppHeader,
    AppMain,
    CardSearcher
  },
  data() {
    return {
      store
      
    };
  },
  methods: {
    getCardsFromApi() {
      console.log(store.searchedStatus)
      let apiUrl = 'https://db.ygoprodeck.com/api/v7/cardinfo.php';
      const queryParams = {
        num: 20,
        offset: 0
      };
      if(store.searchedStatus !== '') {
        queryParams.archetype = store.searchedStatus;
      }
      axios.get(apiUrl, {
        params: queryParams
      })
      .then((response) => {
        store.cards = response.data.data;
      });
    },
    getArchetypeFromApi() {
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
      .then((response) => {
        console.log(response.data);
        store.archetype = response.data;
      });
    }
  },
  mounted() {
    this.getCardsFromApi();
    this.getArchetypeFromApi();
  }
}

</script>



<template>
  <AppHeader></AppHeader>

  <CardSearcher @searchPerformed="getCardsFromApi"></CardSearcher>
  <AppMain></AppMain>
</template>

<style lang="scss">
@use './style/generic';
</style>