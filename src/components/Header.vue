<template>
    <header>
        <h1><router-link to="/">Vente en ligne</router-link></h1>
        <p><router-link to="/basket"><i class="fa-solid icon-basket fa-basket-shopping"></i></router-link></p>
    </header>
</template>

<script>
export default {
    name: 'CompHeader',
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
        margin-bottom: 60px;

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
    }

</style>