<template>
    <div>
        <!-- <form method="#">
            <select name="categories" id="selectCategory" onchange="document.location.href=:id='category'">
                <option value="#selectCategory"> -- Selectionner une catégorie --</option>
                <span :key="index" v-for="(category, index) in categories">
                    <option :value="`#${category.id}` "> {{ category.label }}</option>
                </span>
            </select>
        </form> -->
        <div :key="index" v-for="(category, index) in categories">
                <h2 :id="category.id">{{ category.label }}</h2>
                <productList :categoryId="category.id" :products="products" :productAddBasket="productAddBasket"/>
        </div>
    </div>

</template>

<script>
    import ProductList from "./ProductList.vue";
    export default {
        
        name: 'CategoryList',
        components: { 
            //ProductSingle,
            ProductList
        },
        props: {
            products:Array,
            categories:Array,
            productAddBasket:Function,
        },
    }
</script>

<style lang="scss">
    h2 {
        font-size: 1.5em;
        letter-spacing: 3px;
        text-transform: uppercase;
        color: orange;
        font-weight: 700;
        border-bottom: 1px solid orange;
        margin-bottom: 30px;
    }
    .cards {
        display: flex;
        justify-content: start;
        flex-wrap: wrap;

        .card {
            max-width: 540px;
        }
    } 
</style>