<!-- PARTE VUE JS-->
<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default {
  name: 'App',
  components: {
    AppHeader,
    AppMain
  }
}

</script>

<!-- PARTE HTML -->
<template>
  <AppHeader />
  <AppMain />
</template>
