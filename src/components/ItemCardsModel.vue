<!-- COMPONENTE GENERICO BOX-CARDS - DA UTILIZZARE COME MODELLO BASE PER ALTRI COMPONENTI -->

<!-- PARTE VUE JS-->
<script>

export default {
    name: 'ItemCardsModel',
    props: {
        img: String,
        title: String
    },
    data() {
        return {
        }
    }
}
</script>

<!-- PARTE HTML -->
<template>
    <div class="card"><img v-bind:src="img"></div>
    <h3>{{ title }}</h3>
</template>