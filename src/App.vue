<script setup>
import Hero from "./components/hero.vue";
import Introduction from "./components/Introduction.vue";
import SubscriptionPlans from "./components/SubscriptionPlans.vue";
import LatestTips from "./components/LatestTips.vue";
import Footer from "./components/Footer.vue";
</script>

<template>
  <div class="page">
    <Hero />
    <Introduction />
    <SubscriptionPlans />
    <LatestTips />
    <Footer />
  </div>
</template>

<div id="top" class="page"></div>

<style>
@import url("https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap");

html,
body {
  margin: 0;
  padding: 0;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: "Plus Jakarta Sans", sans-serif;
}

button,
input,
textarea,
select {
  font: inherit;
}

.page {
  min-height: 100vh;
}
</style>
