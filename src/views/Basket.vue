<template>

    <main>
        <h2>Votre panier</h2>

        <div v-if="errorMessageBasket" class="container-errors">
            <img src="../assets/nothing.gif" alt="No product"/>
        </div>

        <div v-else class="container-basket">
            <div>
                <div class="card-basket">
                    <div class="img-product">
                        <img src="../assets/logo.png" alt="Test"/>
                    </div>
                    <div class="container-card-basket">
                        <div class="name-product">Nom du produit</div>
                        <div class="description-product">Description du produit elle doit être un peu plus grande afin de tester les 3 petits points</div>
                        <div class="price-product bg-success text-white">1000€</div>
                        <div class="delete-product bg-danger text-white">
                            <i class="fa-solid fa-trash-can"></i>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>

</template>


<script>

    export default {
        name: 'ViewBasket',
        data() {
            return {
                storageBasketList: [],
                errorMessageBasket: false,
            }
        },

        methods: {
            checkStorage() {
                if (localStorage.product && localStorage.product.length > 0) {
                    this.errorMessageBasket = false;
                    // console.log('Le panier est plein !!!');
                    // console.log(this.storageBasketList);
                    this.storageBasketList = localStorage.product;
                    
                } else {
                    // console.log('Le panier est VIDE !!!');
                    this.errorMessageBasket = true;
                }
            },
        },

        //Page generate
        mounted() {
            this.checkStorage();
        },
    }

</script>


<style lang="scss">
    main {

        h2 {
            font-size: 1.5em;
            letter-spacing: 3px;
            text-transform: uppercase;
            color: orange;
            font-weight: 700;
            margin: 50px 0 20px 0;
        }

        .container-basket, .container-errors {
            padding: 10px;
            margin-top: 5px;
            border-radius: 10px;
            background-color: #FFFFFF;

            .card-basket {
                display: flex;
                flex-direction: column;
                padding: 20px;
                border-bottom: 1px solid grey;

                .img-product {
                    padding: 0;
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    margin-bottom: 10px;

                    img {
                        height: 80px;
                    }
                }

                .container-card-basket {

                    .name-product {
                        color: #2b7daf;
                        font-weight: 700;
                    }

                    .description-product {
                        font-style: italic;
                        margin-bottom: 10px;
                    }

                    .price-product, .delete-product {
                        height: 40px;
                        padding: 10px;
                        display: flex;
                        justify-content: center;
                        border-radius: 10px;
                        margin-top: 10px;
                    }
                }
            }
        }

        .container-errors {
            display: flex;
            justify-content: center;

            img {
                width: 80%;
            }
        }
    }
</style>