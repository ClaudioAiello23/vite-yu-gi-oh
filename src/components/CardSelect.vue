<!-- PARTE VUE JS-->
<script>
import { store } from '../store.js'; //sintassi per l'import del file store.js (la parola store è scritta tra graffe)

export default {
    name: 'CardSelect',
    data() {
        return {
            store
        }
    }
}
</script>

<!-- PARTE HTML -->
<template>
    <div class="container">
        <div class="row">
            <div class="col-2">
                <!--collego la proprietà ereditata da store.js -->
                <select class="form-select my-4" v-model="store.selectArchetype" @change="$emit('SearchArchetype')">
                    <!--inserisco value='' per poter vedere il valore di default "Select an Archetype" al caricamento della pagina -->
                    <option selected value="">Select an Archetype</option>
                    <option>ALIEN</option>
                </select>
            </div>
        </div>
    </div>
</template>

<!-- PARTE SCSS-->
<style lang="scss" scoped></style>