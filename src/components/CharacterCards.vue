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
    <div class="nb_card_container container">
        <div class="row">
            <div class="col-2 nb_article_card_box" v-for="character in characters">
                <ItemCardsModel :img="character.card_images" :name="character.name" :archetype="character.archetype" />
            </div>
        </div>
    </div>
</template>


    <!-- PARTE SCSS-->
<style lang="scss" scoped>
@use '../assets/styles/_partials/_variables.scss' as *;

.nb_card_container {
    background-color: white;
    padding: 3.125rem;

    .nb_article_card_box {
        border: 1px solid black;
        background-color: $primary_color;
    }

}
</style>
