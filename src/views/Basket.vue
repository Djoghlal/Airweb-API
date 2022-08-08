<template>

    <main>
        <h2>Votre panier</h2>
        <h3>Total du panier: {{ priceTotal() }}€</h3>

        <div v-if="errorMessageBasket" class="container-errors">
            <img src="../assets/nothing.gif" alt="No product"/>
        </div>

        <div v-else-if="validShop" class="p-3 mb-2 bg-success text-white">
            <p>Votre commande a bien été effectuée</p>
        </div>

        <div v-else class="container-basket">
            <div :key="index" v-for="(product, index) in storageBasketList">
                <div class="card-basket">
                    <div class="img-product">
                        <img :src="product.thumbnail_url" alt="Test"/>
                    </div>
                    <div class="container-card-basket">
                        <div class="name-product">{{ product.label }}</div>
                        <div class="description-product">{{ product.description }}</div>
                        <div class="price-product bg-success text-white">{{ priceConvert(product.price) }}€</div>
                        <div v-on:click="deleteProduct(product)"  class="delete-product bg-danger text-white">
                            <i class="fa-solid fa-trash-can"></i>
                        </div>
                    </div>
                </div>
            </div>
            <div class="btn-basket">
                <button v-on:click="validBasket" type="button" class="btn btn-primary">Valider ma commande</button>
                <button v-on:click="deleteBasket" type="button" class="btn btn-danger">Effacer le panier</button>
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
                validShop: false,
            }
        },

        methods: {
            priceConvert(priceProduct) {
                return priceProduct / 100; 
            },
            checkStorage() {
                if (localStorage.product && localStorage.product.length > 0) {
                    this.errorMessageBasket = false;
                    // console.log('Le panier est plein !!!');
                    // console.log(this.storageBasketList);
                    this.storageBasketList = JSON.parse(localStorage.product);
                    
                } else {
                    // console.log('Le panier est VIDE !!!');
                    this.errorMessageBasket = true;
                }
            },
            deleteProduct(productTarget) {
                console.log(productTarget);
                // Filter all items where id is not equal to product
                this.storageBasketList = this.storageBasketList.filter((product) => product.id !== productTarget.id);
                if (this.storageBasketList.length <= 0) {
                    localStorage.removeItem('product');
                    this.errorMessageBasket = true;
                } else {
                    this.errorMessageBasket = false;
                    localStorage.setItem('product', JSON.stringify(this.storageBasketList));
                }
            },
            priceTotal() {
                return this.storageBasketList.reduce((totalPrice, product) => {
                    return totalPrice += product.price / 100;
                }, 0);
            },

            validBasket() {
                this.validShop = true;
                localStorage.removeItem('product');
            },

            deleteBasket() {
                if (this.storageBasketList.length > 0) {
                    localStorage.removeItem('product');
                    this.$router.push("/");
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

        h2, h3 {
            letter-spacing: 3px;
            text-transform: uppercase;
            color: orange;
            font-weight: 700;
            
        }
        h2 {
            font-size: 1.5em;
            margin: 50px 0 20px 0;
        }

        h3 {
           font-size: 1.2em; 
           margin: 0 0 20px 0;
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

        .btn-basket {
            display: flex;
            justify-content: center;
            margin: 40px 0;

            button {
                margin-right: 20px;
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