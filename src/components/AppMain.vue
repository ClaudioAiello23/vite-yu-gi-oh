<!-- PARTE VUE JS-->
<script>
import CardSelect from './CardSelect.vue';
import CharacterCards from './CharacterCards.vue';

export default {
    name: 'AppMain',
    components: {
        CardSelect,
        CharacterCards
    }
}
</script>

<!-- PARTE HTML -->
<template>
    <main class="container-fluid">
        <CardSelect />
        <CharacterCards />
    </main>
</template>

<!-- PARTE SCSS-->
<style lang="scss" scoped></style>