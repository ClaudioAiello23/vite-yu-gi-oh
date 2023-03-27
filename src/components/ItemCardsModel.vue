<!-- COMPONENTE GENERICO BOX-CARDS - DA UTILIZZARE COME MODELLO BASE PER ALTRI COMPONENTI -->

<!-- PARTE VUE JS-->
<script>

export default {
    name: 'ItemCardsModel',
    props: {
        image: String,
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
        <div><img v-bind:src="image"></div>
        <h3>{{ name }}</h3>
        <div>{{ archetype }}</div>
    </article>
</template>