<template>
  <div class="home">
    <CardSection />
  </div>
</template>

<script>
// @ is an alias to /src
import CardSection from "@/components/CardSection.vue";

export default {
  name: "HomeView",
  components: {
    CardSection,
  },
};
</script>
