<template>
    <div class="row g-0 structure-card">
        <div class="col-md-4 container-img">
            <img :src="checkPic" class="img-fluid rounded-start" alt="Image">
        </div>
        <div class="col-md-8">
            <div class="card-body">
                <h5 class="card-title">{{ product.label }}</h5>
                <p class="card-text">{{ product.description }}</p>
                <div class="card-bottom">
                    <p class="bg-success text-white card-price">{{ priceConvert(product.price) }}€</p>
                    <p><i v-on:click="$emit('productAddBasket', product)" class="fa-solid fa-cart-plus card-icon-product"></i></p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'ProductSingle',
        
        // props: ["product"], 
        props: {
            product:Object
        },
        methods: {
            priceConvert(priceProduct) {
                return priceProduct / 100; 
            }
        },
        computed: {
            checkPic() {
                if (this.product !== undefined && this.product.thumbnail_url === null) {
                    return require('../assets/unknow.png');
                } else {
                    return this.product.thumbnail_url;
                }
            }
        },
    }
</script>

<style lang="scss">
    .structure-card {
        padding: 0;

        .container-img {
            height: 100%;
            padding: 5px;

            img {
                width: 100%;
                height: 200px;
                object-fit: cover;
                border-radius: 10px;
            }
        }

        .card-title {
            color: #2b7daf;
        }

        .card-text {
            max-width: 100%;
            height: 130px;
        }

        .card-bottom {
            display: flex;
            align-items: end;
            justify-content: space-between;

            .card-price {
                width: 90px;
                padding: 15px;
                display: flex;
                justify-content: center;
                border-radius: 10px;
            }

            .card-icon-product {
                margin: 0 40px 0 0;
                font-size: 1.8em;
                color: #2b7daf;
            }
        }
    }


    @media (min-width: 1024px) {
        .card-title {
            height: 50px;
        }

        .card-text {
            max-width: 100%;
            height: 135px;
        }
    }
    
</style>