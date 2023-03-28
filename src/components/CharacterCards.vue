<!-- PARTE VUE JS-->
<script>
import { store } from '../store.js'; //sintassi per l'import del file store.js (la parola store è scritta tra graffe)

import ItemCardsModel from './ItemCardsModel.vue';

export default {
    name: 'CharacterCards',
    components: {
        ItemCardsModel
    },
    data() {
        return {
            store
        }
    }
}
</script>

<!-- PARTE HTML -->
<template>
    <div class="nb_found_cards_box py-3 fw-bold container ">Found {{ store.characters.length }} cards</div>
    <div class="nb_card_container container">
        <div class="row justify-content-between">
            <div class=" nb_article_card_box text-center col-2" v-for="character in store.characters.slice(0, 50)">
                <!-- NB slice(0, 50) mi fa vedere nel Dom 50 cards su 12461 -->
                <ItemCardsModel v-bind:img="character.card_images[0].image_url_small" v-bind:name="character.name"
                    v-bind:archetype="character.archetype" />
            </div>
        </div>
    </div>
</template>


    <!-- PARTE SCSS-->
<style lang="scss">
@use '../assets/styles/_partials/_variables.scss' as *;

.single_card_box {
    padding-bottom: .9375rem;

    img {
        width: 100%;
        height: 100%;
    }
}

.nb_found_cards_box {
    background-color: #212529;
    color: $secondary_color;
}

.nb_card_container {
    background-color: $secondary_color;
    padding-bottom: .625rem;

    .nb_article_card_box {
        background-color: $primary_color;
        width: calc(100% / 5);
        padding-bottom: 1.25rem;


        h5 {
            color: $secondary_color;
            text-align: center;
            padding-bottom: .625rem;
        }
    }
}
</style>
