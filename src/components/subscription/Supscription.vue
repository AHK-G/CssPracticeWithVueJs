<script setup lang="ts">
import { ref } from "vue";
import Form from "../form/Form.vue";
import circle from "../../assets/circle.png";
import Players from "../../assets/Players.png";
import big from "../../assets/big.png";
import plus from "../../assets/plus.png";

const selectedColor = ref<string | null>(null);
const isFormOpen = ref(false);
const isImageVisible = ref(true);

const colorFunction = (color: string) => {
  if (selectedColor.value === color) {
    selectedColor.value = null;
    isFormOpen.value = false;
    isImageVisible.value = true;
  } else {
    selectedColor.value = color;
    isFormOpen.value = true;
    isImageVisible.value = false;
  }
};

const titleContainer = "This will be a translation key. You can add any text here";

const subscriptionOptions = [
  {
    label: "Annual Pass",
    value: "yearly",
    price: "$114.95",
    period: "Per Year",
    description: "ACCESS TO BIG TEN NETWORK+ FOR ONE YEAR",
  },
  {
    label: "Monthly Pass",
    value: "monthly",
    price: "$14.95",
    period: "Per Month",
    description: "ACCESS TO BIG TEN NETWORK+ FOR ONE MONTH",
  },
];
</script>

<template>
  <div
    :class="isImageVisible ? 'subscriptionContainer visible' : 'subscriptionContainer hidden'"
  >
      <div class="titleContainer">
        <p class="mobileTitle">{{ titleContainer }}</p>
      </div>

    <div class="rightImage">
      <div v-if="isImageVisible" class="imageSection">
        <img class="playersImage" :src="Players" alt="Players" />
        <div class="rectangle">
          <img :src="big" alt="big" class="rectangleBig" />
          <img :src="plus" alt="plus" class="rectanglePlus" />
        </div>
      </div>
    </div>

    <div class="left">

      <div class="titleContainer">
        <p class="desktopTitle">{{ titleContainer }}</p>
      </div>
      <h3 class="headerText">
        SELECT YOUR GIFT OPTIONS
      </h3>
      <div id="bestValue" >Best Value</div>
 
      <div
        v-for="option in subscriptionOptions"
        :key="option.value"
        @click="colorFunction(option.value)"
        :class="['subContainer', { active: selectedColor === option.value }, option.value]"
      >

        <img class="circle" :src="circle" alt="circle" />
        <div class="subsubContainer">
          <p :class="`${option.value}Pass`">
            {{ option.label }}
            <span class="price">
              {{ option.price }} <span class="perTime">{{ option.period }}</span>
            </span>
          </p>
          <p class="access">{{ option.description }}</p>
        </div>
      </div>
    </div>

    <div class="rightForm">
      <Form v-if="isFormOpen" />
    </div>
  </div>
</template>

<style >
@import "./Supscription.css";
</style>