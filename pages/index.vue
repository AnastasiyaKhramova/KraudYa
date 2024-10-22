<template>
  <div>
    <Header />
    <Marquee />
    <Lection />
    <Transformation />
    <Player />
    <Marquee />
    <Footer />


  </div>
</template>

<script lang="ts" setup>
import Marquee from "~/components/Marquee.vue";
import Header from "../layouts/Header.vue";
import Lection from "~/components/Lection.vue";
import Transformation from "~/components/Transformation.vue";
import Player from "~/components/Player.vue";
import Footer from "~/layouts/Footer.vue";
</script>

<style>

</style>
