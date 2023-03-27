<!-- PARTE VUE JS-->
<script>
import ItemCardsModel from './ItemCardsModel.vue';
import axios from 'axios';

export default {
    name: 'CharacterCards',
    components: {
        ItemCardsModel
    },
    data() {
        return {
            characters: []
        }
    },
    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
            .then((response) => {
                console.log(response);
                this.characters = (response.data.data);
            })
    }
}
</script>

<!-- PARTE HTML -->
<template>
    <div class="nb_found_cards_box py-3 fw-bold container ">Found TOT cards</div>
    <div class="nb_card_container container">
        <div class="row justify-content-center">
            <div class="nb_article_card_box col-2 mb-3 mx-3" v-for="character in characters">
                <ItemCardsModel :img="character.card_images" :name="character.name" :archetype="character.archetype" />
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
    padding-bottom: 3.125rem;

    .nb_article_card_box {
        border: 1px solid black;
        background-color: $primary_color;

        h4 {
            color: $secondary_color;
        }
    }

}
</style>
