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
        <div class="container-cards" :key="index" v-for="(category, index) in categories">
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
    
    .container-cards {
        display: flex;
        flex-direction: column;
        justify-content: start;
        flex-wrap: wrap;

        h2 {
            font-size: 1.5em;
            letter-spacing: 3px;
            text-transform: uppercase;
            color: orange;
            font-weight: 700;
            margin: 50px 0 20px 0;
        }
    } 
</style>