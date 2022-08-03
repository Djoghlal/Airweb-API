<template>

    <main>
        <CategoryList :products="products" :categories="categories" :productAddBasket="productAddBasket"/>
    </main>

</template>


<script>
    import CategoryList from '../components/CategoryList.vue';
    import axios from 'axios';

    export default {
        name: 'ViewMain',
        components: {
            CategoryList,
        },

        data() {
            return {
                products: null,
                categories: null,
                basketList: [],
            }
        },

        methods: {
            productList() {
                axios
                .get('http://localhost:3000/products')
                .then((response) => {
                    this.products = response.data;
                    console.log(this.products);
                });
            },

            categoryList() {
                axios
                .get('http://localhost:3000/categories')
                .then((response) => {
                    this.categories = response.data;
                    console.log(this.categories);
                });
            },

            productAddBasket(item) {
                console.log(item);
                this.basketList.push(item);
                localStorage.setItem('product', JSON.stringify(this.basketList));
            },
        },

        mounted() {
            this.productList();
            this.categoryList();
        },
    }

</script>


<style lang="scss">
    main {
        padding: 20px;
    }
</style>