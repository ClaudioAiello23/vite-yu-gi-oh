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
    <CharacterCards />
</template>

<!-- PARTE SCSS-->
<style lang="scss" scoped></style>