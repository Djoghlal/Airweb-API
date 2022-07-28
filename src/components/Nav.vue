<template>
    <nav>
        <img src="../assets/logo.png" alt="Shopping"/>
        <ul>
            <a href="#"><li>Lien 1</li></a>
            <a href="#"><li>Lien 2</li></a>
            <a href="#"><li>Lien 3</li></a>
            <a href="#"><li>Lien 4</li></a>
        </ul>
    </nav>
</template>

<script>
export default {
    name: 'CompNav',
}
</script>

<style lang="scss">
    nav {
        height: 100vh;
        width: 150px;
        background-color: rgba(255, 255, 255, .5);

        img {
            width: 90px;
            height: 90px;
        }
    }
</style>