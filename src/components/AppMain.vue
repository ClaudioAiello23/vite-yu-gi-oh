<!-- PARTE VUE JS-->
<script>
import CardSelect from './CardSelect.vue';
import CharacterCards from './CharacterCards.vue';

export default {
    name: 'AppMain',
    components: {
        CardSelect,
        CharacterCards
    },
    methods: {
        // funzione che prende $emit segnalato dal figlio CardSelect.vue e lo passa al padre AppMain.vue
        selectOption() {
            console.log('ho ascoltato questo evento');
            this.$emit('searchFinal');
        }
    }
}
</script>

<!-- PARTE HTML -->
<template>
    <main class="container-fluid">
        <CardSelect @SearchArchetype="selectOption" />
        <CharacterCards />
    </main>
</template>

<!-- PARTE SCSS-->
<style lang="scss" scoped></style>