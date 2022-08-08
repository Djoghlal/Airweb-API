<template>
    <header>
        <h1><router-link to="/">Vente en ligne</router-link></h1>
        <p>
            <span class="number-basket">{{ calculBasketLength }}</span>
            <router-link to="/basket">
                <i class="fa-solid icon-basket fa-basket-shopping"></i>
            </router-link>
        </p>
    </header>
</template>

<script>
export default {
    name: 'CompHeader',
    computed: {
        calculBasketLength() {
            if (localStorage.product) {
                return JSON.parse(localStorage.product).length;
            } else {
                return 0;
            }
        }
    },
}
</script>

<style lang="scss">

    header {
        height: 60px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: rgba($color: #FFFFFF, $alpha: 0.6);
        padding: 0 15px 0 15px;
        border-radius: 0 0 20px 20px;

        h1, p {
            margin: 0px;
        }

        h1, .icon-basket {
            font-size: 1.5em;
            color: #2b7daf;
        }

        h1 > * {
            font-weight: 100;
            text-decoration: none;
            letter-spacing: 3px;
            text-transform: uppercase;
            text-decoration: none;
            color: #2b7daf;
        }

        .number-basket {
            width: 10px;
            height: 10px;
            background: red;
            padding: 5px 10px;
            border-radius: 50%;
            color: #FFFFFF;
            text-decoration: none;
            font-weight: 700;
            margin: 0 7px 0 0;
        }
    }

</style>