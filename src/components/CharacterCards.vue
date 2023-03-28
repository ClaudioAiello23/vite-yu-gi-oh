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
        <div class="row justify-content-center">
            <div class="nb_article_card_box col-2 mb-3 mx-3" v-for="(character, index) in store.characters.slice(0, 50)">
                <!-- NB slice(0, 50) mi fa vedere nel Dom 50 cards su 12461 -->
                <ItemCardsModel v-bind:img="character.card_images[0].image_url" v-bind:name="character.name"
                    v-bind:archetype="character.archetype" />
            </div>
        </div>
    </div>
</template>


    <!-- PARTE SCSS-->
<style lang="scss">
@use '../assets/styles/_partials/_variables.scss' as *;

.nb_found_cards_box {
    background-color: #212529;
    color: $secondary_color;
}

.nb_card_container {
    background-color: $secondary_color;
    padding-bottom: .625rem;

    .nb_article_card_box {
        background-color: $primary_color;

        h4 {
            color: $secondary_color;
        }
    }
}
</style>
