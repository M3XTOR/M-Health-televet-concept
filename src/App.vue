<script setup>
import Footer from "./components/layout/Footer.vue";
</script>

<template>
  <div class="page">
    <RouterView />
    <Footer />
  </div>
</template>

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