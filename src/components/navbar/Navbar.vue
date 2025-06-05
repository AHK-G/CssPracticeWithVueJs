<script setup lang="ts">
import lines from "../../assets/navbar.png";
import search from "../../assets/search.png";
import big from "../../assets/big.png";
import dropDown from "../../assets/dropDown.png";
import searchLine from "../../assets/searchLine.png";
import plus from "../../assets/plus.png";

import { ref } from "vue";

const navLinks = ref([
  { name: "Home", url: "#" },
  { name: "Event Calendar", url: "#" },
  { name: "Video Library", url: "#" },
  { name: "Channels", url: "#" },
  { name: "More", url: "#", hasDropdown: true }
]);
</script>

<template>
  <nav class="navbar">
    <img :src="lines" alt="lines" class="navbarImage lines" />
    <div>
      <img :src="big" alt="big" class="navbarImage" />
      <img :src="plus" alt="plus" class="plus" />
    </div>
    <img :src="search" alt="smallSearch" class="navbarImage smallSearch" />

    <div class="navLinks">
      <a
        v-for=" link in navLinks"
        :href="link.url"
        class="link"
      >
        {{ link.name }}
        <img
          v-if="link.hasDropdown"
          :src="dropDown"
          alt="moreDropDown"
          class="moreDropDown"
        />
      </a>

    <!-- <div class="navLinks">
      <a href="#" class="link">Home</a>
      <a href="#" class="link">Event Calendar</a>
      <a href="#" class="link">Video Library</a>
      <a href="#" class="link">Channels</a>
      <a href="#" class="link">
        More
        <img :src="dropDown" alt="moreDropDown" class="moreDropDown" />
      </a>
    </div> -->
  </div>

    <div class="navLinksRight">
      <div>
        <img :src="big" alt="bigRight" class="bigRight" />
        <img :src="dropDown" alt="bigDropDown" class="bigDropDown" />
      </div>

      <div class="search">
        <img :src="search" alt="searchIcon" class="searchIcon" />
        <img :src="searchLine" alt="searchLine" class="searchLine" />
      </div>
      <a href="#" class="signIn">Sign-In</a>
    </div>
  </nav>
</template>

<style>
@import "./Navbar.css";
</style>
