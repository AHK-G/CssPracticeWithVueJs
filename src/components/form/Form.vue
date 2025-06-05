<script setup lang="ts">
import { ref } from "vue";
import gift from "../../assets/gift.png";

const error = ref("");
const email = ref("");

const sendButton = (e: Event) => {
  e.preventDefault();
  if (!email.value.includes("@")) {
    error.value = "An email address must contain a single @";
    return;
  } else {
    error.value = "";
  }
};
</script>

<template>
  <form class="formContainer">
    <img class="gift" :src="gift" alt="gift" />
    <p class="rec">Recipient’s Details</p>

    <div class="gridWrapper">
      <label class="inputLabel">
        <span>
          First Name <span class="requiredStar">*</span>
        </span>
        <input class="grid1 gridBox" type="text" />
      </label>
      <label class="inputLabel">
        <span>
          Last Name <span class="requiredStar">*</span>
        </span>
        <input class="grid2 gridBox" type="text" />
      </label>
      <label class="inputLabel">
        <span>
          Your Email <span class="requiredStar">*</span>
        </span>
        <input
          class="grid3 gridBox"
          type="email"
          v-model="email"
          :placeholder="error ? 'johndoegmail.com' : ''"
        />
        <p v-if="error" class="error-message">{{ error }}</p>
      </label>
      <label class="inputLabel">
        <span>
          Delivery Date <span class="requiredStar">*</span>
        </span>
        <input class="grid4 gridBox" type="date" />
      </label>
      <label class="inputLabel fullWidth">
        <span>
          Recipient's Email <span class="requiredStar">*</span>
        </span>
        <input class="grid5 gridBox" type="text" />
      </label>
      <label class="inputLabel fullWidth">
        <span>Add a note (Maximum 255 characters)</span>
        <textarea class="grid6 gridBox"></textarea>
      </label>
    </div>

    <button class="sendAGift" @click="sendButton">SEND A GIFT</button>
  </form>
</template>

<style>
@import "./Form.css";
</style>