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
            console.log('AppMain ha ascoltato evento girato da CardSelect.vue');
            this.$emit('searchFinal');
        }
    }
}
</script>

<!-- PARTE HTML -->
<template>
    <main class="container-fluid">
        <CardSelect @searchArchetype="selectOption" />
        <CharacterCards />
    </main>
</template>

<!-- PARTE SCSS-->
<style lang="scss" scoped></style>