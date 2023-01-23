<!-- template tag used for create reusable components contain a container for all html tag -->
<template>
  <!-- div tag for parent card each product section -->
  <div class="container">
    <!-- child card each product section -->
    <div class="main">
      <!-- image each product section -->
      <div class="image">
        <!-- img tag used for data binding with call API from fakestoreapi for render image each product -->
        <img :src="products.image" :alt="products.category" />
      </div>
      <!-- description each product section -->
      <div class="description">
        <!-- heading tag used for data binding with call API from fakestoreapi for render title each product -->
        <h4
          :class="[
            products.category == 'men\'s clothing'
              ? 'color-men'
              : 'color-women',
          ]"
        >
          {{ products.title }}
        </h4>
        <!-- category, rating-rate, description each product section -->
        <div class="product-rate">
          <!-- p tag used for call API from fakestoreapi through props for render category each product -->
          <p class="product-category">{{ products.category }}</p>
          <!-- each circle rating-rate products section -->
          <div
            :class="[
              products.category == 'men\'s clothing'
                ? 'color-rate-men'
                : 'color-rate-women',
            ]"
          >
            <!-- this tag used for call API from fakestoreapi through props for render rating-rate each product -->
            <p class="rate">{{ products.rating.rate }}/5</p>
            <!-- this tag used for call API from fakestoreapi through props for render each circle rating-rate color icon less or more than rating-rate  -->
            <div
              :class="[
                Math.round(products.rating.rate) > 0
                  ? 'circle bg-color'
                  : 'circle',
              ]"
            ></div>
            <div
              :class="[
                Math.round(products.rating.rate) > 1
                  ? 'circle bg-color'
                  : 'circle',
              ]"
            ></div>
            <div
              :class="[
                Math.round(products.rating.rate) > 2
                  ? 'circle bg-color'
                  : 'circle',
              ]"
            ></div>
            <div
              :class="[
                Math.round(products.rating.rate) > 3
                  ? 'circle bg-color'
                  : 'circle',
              ]"
            ></div>
            <div
              :class="[
                Math.round(products.rating.rate) > 4
                  ? 'circle bg-color'
                  : 'circle',
              ]"
            ></div>
          </div>
        </div>

        <hr />
        <p class="desk">{{ products.description }}</p>
      </div>
    </div>
  </div>
</template>

<!-- script tag for interactive ecommerce web vue project -->
<script>
export default {
  name: "CardSection",
  data() {
    return {};
  },
  // props declaration for communicates between parent and child components
  props: ["products", "increments"],
};
</script>

<!-- style tag for style web -->
<style scoped>
@import "../assets/style/CardSection.css";
</style>
