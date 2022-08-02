<template>
    <header>
        <h1>Vente en ligne</h1>
        <p><i class="fa-solid icon-basket fa-basket-shopping"></i></p>
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

        h1 {
            font-weight: 100;
            text-decoration: none;
            letter-spacing: 3px;
            text-transform: uppercase;
            
        }


    }

</style>