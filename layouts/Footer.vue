<template>
    <footer class="container">
        <div class="footer">
            <h3>Все персонажи, события и цитаты являются вымышленными и не принадлежат создателям сайта. С подробностями можно познакомиться в главе XXXIV романа Ильи Ильфа и Евгения Петрова «Двенадцать стульев».</h3>
        </div>
    </footer>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.footer {
    height: 150px;
    background: #E9DED4;
    display: flex;
    align-items: center;
    
    & h3 {
        padding: 40px 72px 72px;
        color: $textcolor-dark;
        font-size: 1rem;
        font-family: $title-font;
        font-weight: normal;
        opacity: 60%;
        margin: 0 auto;
    }
}

</style>