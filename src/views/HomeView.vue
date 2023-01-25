<!-- template tag used for create reusable components contain a container for all html tag -->
<template>
  <!-- div tag used for parent each men, women, unavailable card product border limit page -->
  <div>
    <!-- renders child each men, women, unavailable card product border limit page -->
    <div class="container-product-men">
      <div>
        <!-- loadersection tag is used for render if the directive's expression returns a truthy value -->
        <LoaderSection v-if="load" />
        <!-- render if the directive's expression returns a false value -->
        <div v-else>
          <CardUnavailable
            v-if="background == 2"
            :product="products"
            :increment="increment"
          />
          <CardSection v-else :product="products" :increment="increment" />
        </div>
      </div>
    </div>
    <!-- this tag use conditional rendering for background pattern each men, women, unavailable product -->
    <div class="bg-pattern-men" v-if="background == 0"></div>
    <div class="bg-pattern-women" v-else-if="background === 1"></div>
    <div class="bg=pattern-unavailable" v-else></div>
  </div>
</template>

<!-- script tag for interactive ecommerce web vue project -->
<script>
// @ is an alias to /src
// import file from name folder components
import CardSection from "@/components/CardSection.vue";
import CardUnavailable from "@/components/CardUnavailable.vue";
import LoaderSection from "@/components/LoaderSection.vue";
// import library open source from dependency for request data through fakestoreapi

export default {
  // name component for export file
  name: "HomeView",
  // components used for register name component through import file
  components: {
    CardSection,
    CardUnavailable,
    LoaderSection,
  },
  data() {
    return {
      load: true,
      products: [],
      background: 0,
    };
  },
};
</script>

<!-- style tag for style web -->
<style>
/* import file from name folder style  */
@import "../assets/style/HomeView.css";
</style>
