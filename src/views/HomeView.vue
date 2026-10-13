<script setup>
import Hero from "../components/home/Hero.vue";
import Introduction from "../components/home/Introduction.vue";
import SubscriptionPlans from "../components/home/SubscriptionPlans.vue";
import LatestTips from "../components/home/LatestTips.vue";
</script>

<template>
  <main id="top" class="home-page">
    <Hero />
    <Introduction />
    <SubscriptionPlans />
    <LatestTips />
  </main>
</template>

<style scoped>
.home-page {
  min-height: 100vh;
}
</style>