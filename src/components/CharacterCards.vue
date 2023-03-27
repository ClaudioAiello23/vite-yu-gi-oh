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
            characters: ['ciao']
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
    <div class="container-fluid">
        <div class="row">
            <div class="col-2 nb_article-card ">
                <ItemCardsModel />
                <div>{{ characters[0].name }}</div>
            </div>
        </div>
    </div>
</template>

<!-- PARTE SCSS-->
<style lang="scss" scoped>
.nb_article-card {
    border: 1px solid black;
}
</style>