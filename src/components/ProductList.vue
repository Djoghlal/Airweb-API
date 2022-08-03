<template>
    <div class="cards">
        <div :key="index" v-for="(product, index) in productList" class="card mb-3 card">
            <!-- left = child AND right of = Parent -->
            <!-- @ child sending to parent -->
            <ProductSingle :product="product" @productAddBasket="productAddBasket"/>
        </div>
    </div>
</template>

<script>
    import ProductSingle from "./ProductSingle.vue";
    export default {
        name: 'productList',
        props: {
            categoryId:String,
            products:Array,
            productAddBasket:Function,
        },
        components: {
            ProductSingle,
        },
        computed: {
            productList() {  
                if (this.products !== undefined) {
                    return this.products.filter((product) => 
                    product.category_id === this.categoryId)
                } else {
                    return [];
                }
            }
        }
    }
</script>

<style lang="scss">

    .card {
        margin-right: 40px;
    }

</style>