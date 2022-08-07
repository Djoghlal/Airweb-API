<template>
    <div class="list-cards">
        <div :key="index" v-for="(product, index) in productList" class="card mb-3">
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
                if (this.products !== undefined && this.products.length > 0) {
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
        width: 100%;
        padding: 0;
        border-radius: 10px !important;
    }

    @media (min-width: 1024px) {
        .list-cards {
            display: flex;
            flex-wrap: wrap;

            .card {
                width: 450px;
                margin-right: 30px;
            }
        }
    }
</style>