<!-- COMPONENTE GENERICO BOX-CARDS - DA UTILIZZARE COME MODELLO BASE PER ALTRI COMPONENTI -->

<!-- PARTE VUE JS-->
<script>

export default {
    name: 'ItemCardsModel',
    props: {
        img: String,
        name: String,
        archetype: String
    },
    data() {
        return {
        }
    }
}
</script>

<!-- PARTE HTML -->
<template>
    <div class="single_card_box"><img v-bind:src="img"></div>
    <h5>{{ name }}</h5>
    <div>{{ archetype }}</div>
</template>