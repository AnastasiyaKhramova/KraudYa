<template>
    <header class="container header">
        <div class="second-container">
            <div class="logo">
                <img v-for="(n, index) in 4" :key="index" src="../assets/img/logo.png" alt="logo" />
                <p>клуб четырех коней</p>
            </div>
        </div>
    </header>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.header {
    height: 700px;
    background: url(../assets/img/main_desktop.png);
}
</style>