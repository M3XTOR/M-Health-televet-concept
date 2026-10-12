<script setup>
import Navbar from "./Navbar.vue";
</script>

<template>
  <section class="hero">
    <Navbar />

    <div class="hero-content">
      <h1>
        Welcome to
        <span class="no-break">M-Health</span>
        <span class="no-break">TeleVet</span>
      </h1>

      <p>
        Discove animal care tips, trivia, and expert insights to help you care
        for your animals.
      </p>

      <a href="#animal-care-tips" class="hero-cta">
        Explore Animal Care Tips
      </a>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  min-height: 100dvh;

  background-image: url("/images/hero-background.jpg");
  background-size: cover;
  background-position: center center;
  background-repeat: no-repeat;

  display: flex;
  flex-direction: column;
}

.hero-content {
  width: min(560px, 90%);
  margin-left: 6%;
  margin-top: clamp(70px, 12vh, 150px);
}

.hero-content h1 {
  color: #ffffff;
  font-size: clamp(36px, 4vw, 56px);
  font-weight: 700;
  line-height: 1.15;
  margin: 0;
}

.hero-content p {
  color: #f3f6fa;
  font-size: 16px;
  line-height: 1.6;
  margin-top: 20px;
}
.hero-cta {
  display: inline-block;
  margin-top: 28px;
  padding: 14px 28px;

  background-color: #d93645;
  color: #ffffff;

  font-size: 16px;
  font-weight: 600;
  text-decoration: none;

  border-radius: 6px;

  transition:
    transform 0.25s ease,
    background-color 0.25s ease;
}

.hero-cta:hover {
  background-color: #c52c3b;
  transform: translateY(-3px);
}
.no-break {
  white-space: nowrap;
}

@media (max-width: 768px) {
  .hero {
    background-image: url("/images/hero-mobile.jpg");
    background-position: center center;
  }

  .hero-content {
    width: 88%;
    margin-left: 6%;
    margin-top: clamp(90px, 15vh, 160px);
  }

  .hero-content h1 {
    font-size: clamp(30px, 8vw, 36px);
    line-height: 1.15;
  }

  .hero-content p {
    font-size: 15px;
    line-height: 1.5;
    margin-top: 14px;
    background-color: rgba(7, 26, 51, 0.65);
    padding: 10px 14px;
    border-radius: 8px;
    max-width: 100%;
    width: fit-content;
    box-sizing: border-box;
  }

  .hero-cta {
    margin-top: 22px;
  }
}
</style>
