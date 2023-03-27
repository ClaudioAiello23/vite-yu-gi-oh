<!-- PARTE VUE JS-->
<script>

export default {
    name: 'AppHeader'
}
</script>

<!-- PARTE HTML -->
<template>
    <header>
        <div class="container-fluid d-flex align-items-center">
            <div class="nb_logo_box mx-3"><img class=img-fluid src="../../public/images/yugioh.webp" alt="logo"></div>
            <h1>Yu-Gi-Oh Api</h1>
        </div>
    </header>
</template>

<!-- PARTE SCSS-->
<style lang="scss" scoped>
header {
    padding: 1.25rem 0;
    background-color: white;

    .nb_logo_box {
        width: 3.125rem;
        height: 1.875rem;

    }
}
</style>