<template>

    <main>
        <ItemsList/>
    </main>

</template>


<script>
    import ItemsList from '../components/ItemsList.vue';

    export default {
        name: 'ViewMain',
        components: {
            ItemsList,
        }
    }

</script>


<style lang="scss">
    main {
        border: 1px solid blue;
    }
</style>