<script setup lang="ts">
import big from "../../assets/big.png";
import plus from "../../assets/plus.png";
</script>

<template>
  <footer class="footer">
    <img :src="big" alt="Footer Image" class="footerImageBig" />
    <img :src="plus" alt="Footer Image" class="footerImagePlus" />
    <a class="footerElement" href="#">Privacy Policy</a>
    <a class="footerElement" href="#">Customer Support</a>
    <a class="footerElement" href="#">Terms of Service</a>
  </footer>
</template>

<style>
@import "./Footer.css";
</style>
