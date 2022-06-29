<template>
    <div class="card">
        <div class="card-image">
            <figure class="image is-square">
            <img :src="product.src" :alt="product.name">
            </figure>
        </div>
        <div class="card-content">
            <div class="media">
            <div class="media-left">
                <figure class="image is-48x48">
                <img :src="product.src" :alt="product.name">
                </figure>
            </div>
            <div class="media-content">
                <p class="title is-4">{{product.name}}</p>
                <p v-if="product.inventory > 10" class="subtitle is-6 tag is-success">Disponibile</p>
                <p v-else-if="product.inventory > 0 && product.inventory <= 10" class="subtitle is-6 tag is-warning">Quasi esaurito</p>
                <p v-else class="subtitle is-6 tag is-danger">Non disponibile</p>
                <br>
                <p class="subtitle is-6">{{product.price}}€</p>
            </div>
            </div>

            <div class="content">
            {{product.description}} 
            <a>@bulmaio</a>.
            <a href="#">#css</a> <a href="#">#responsive</a>
            </div>
        </div>
    </div> 
</template>

<script>
export default {
    name: "Product",
    props: {
        product: {
            type: Object
        }
    },
}
</script>

<style scoped lang="scss">

</style>