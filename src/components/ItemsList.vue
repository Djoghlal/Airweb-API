<template>

    <div class="cards">
        <div :key="index" v-for="(product, index) in list" class="card mb-3">
            <!-- left = child AND right of = Parent -->
            <ProductSingle :product="product"/>
        </div>
    </div>

</template>

<script>
    import axios from 'axios';
    import ProductSingle from "./ProductSingle.vue";

    export default {
        
        name: 'ItemsList',
        components: { 
            ProductSingle 
        },

        data() {
            return {
                list: null,
            }
        },

        mounted() {
            axios
            .get('http://localhost:3000/products')
            .then((response) => {
                this.list = response.data;
                console.log(this.list);
            });
        },
    }
</script>

<style lang="scss">
    .cards {
        display: flex;
        justify-content: space-around;
        flex-wrap: wrap;

        .card {
            max-width: 540px;
        }
    } 
</style>