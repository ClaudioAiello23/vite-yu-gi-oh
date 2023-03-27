<!-- PARTE VUE JS-->
<script>
import CharacterCards from './CharacterCards.vue';

export default {
    name: 'AppMain',
    components: {
        CharacterCards
    }
}
</script>

<!-- PARTE HTML -->
<template>
    <main class="container-fluid">
        <CharacterCards />
    </main>
</template>

<!-- PARTE SCSS-->
<style lang="scss" scoped>
main {
    margin-top: 100px;
}
</style>