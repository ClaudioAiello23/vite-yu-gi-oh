<!-- PARTE VUE JS-->
<script>
import axios from 'axios';

import { store } from './store.js'; //sintassi per l'import del file store.js (la parola store è scritta tra graffe)

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default {
  name: 'App',
  components: {
    AppHeader,
    AppMain
  },
  data() {
    return {
      store
    }
  },
  methods: {
    search() {
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then((response) => {
          console.log(response);
          this.store.selectArchetype = response.data;
        })
    }
  },
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
      .then((response) => {
        console.log(response);
        this.store.characters = (response.data.data);
        this.store.charactersFound = (response.data.data.length);
      })

    this.search()
  }
}
</script>

<!-- PARTE HTML -->
<template>
  <AppHeader />
  <AppMain @searchFinal="search" />
</template>
