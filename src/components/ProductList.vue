<template>
    <div class="columns">
        <div class="column is-3" v-for="product in products" :key="product.id">
          <Product :product="product"/>
        </div>
    </div>
</template>

<script>
import Product from "./Product.vue"
export default {
    name: "ProductList",
    props: ["products"],
    components: {
      Product
    }
}
</script>

<style scoped lang="scss">

</style>