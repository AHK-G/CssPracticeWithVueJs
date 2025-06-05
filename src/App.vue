<script setup lang="ts">
import Navbar from "./components/navbar/Navbar.vue";
import Subscription from "./components/subscription/Supscription.vue";
import Footer from "./components/footer/Footer.vue";
</script>

<template>
  <div class="appContainer">
    <Navbar />
    <Subscription />
    <Footer />
  </div>
</template>

<style>
@import "./App.css";
</style>