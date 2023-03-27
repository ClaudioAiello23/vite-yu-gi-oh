<!-- PARTE VUE JS-->
<script>
import AppHeader from './components/AppHeader.vue';
import CharacterCards from './components/CharacterCards.vue';

export default {
  name: 'App',
  components: {
    AppHeader,
    CharacterCards
  }
}

</script>

<!-- PARTE HTML -->
<template>
  <AppHeader />
  <CharacterCards />
</template>
