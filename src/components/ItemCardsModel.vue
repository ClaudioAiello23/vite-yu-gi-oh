<!-- COMPONENTE GENERICO BOX-CARDS - DA UTILIZZARE COME MODELLO BASE PER ALTRI COMPONENTI -->

<!-- PARTE VUE JS-->
<script>

export default {
    name: 'ItemCardsModel',
    props: {
        card_images: String,
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
    <article>
        <div><img v-bind:src="card_images"></div>
        <h4>{{ name }}</h4>
        <div>{{ archetype }}</div>
    </article>
</template>