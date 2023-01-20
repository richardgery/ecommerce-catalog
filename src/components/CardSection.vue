<template>
  <div class="container">
    <div class="main">
      <div class="image">
        <img :src="products.image" :alt="altText" />
      </div>
      <div class="description">
        <h4
          :class="[
            products.category == 'men\'s clothing'
              ? 'color-men'
              : 'color-women',
          ]"
        >
          {{ products.title }}
        </h4>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardSection",
  data() {
    return {
      altText: "women or men products image",
    };
  },
  props: ["products", "increments"],
};
</script>

<style>
@import "../assets/style/CardSection.css";
</style>
