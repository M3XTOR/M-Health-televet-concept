<script setup>
import { ref } from "vue";

const activeSection = ref("Home");
const isMenuOpen = ref(false);

const sections = ["Home", "Today's Tip", "Today's Trivia", "Expert Profiles"];

function selectSection(section) {
  activeSection.value = section;
  isMenuOpen.value = false;
}
</script>

<template>
  <nav class="navbar">
    <div class="brand">M-Health</div>

    <div class="nav-links">
      <a
        v-for="section in sections"
        :key="section"
        href="#"
        class="nav-link"
        :class="{ active: activeSection === section }"
        @click.prevent="selectSection(section)"
      >
        {{ section }}
      </a>
    </div>

    <button class="login-button">Login</button>
    <button
      class="menu-toggle"
      type="button"
      :aria-expanded="isMenuOpen"
      aria-controls="mobile-navigation"
      :aria-label="isMenuOpen ? 'Close menu' : 'Open menu'"
      @click="isMenuOpen = !isMenuOpen"
    >
      <span></span>
      <span></span>
      <span></span>
    </button>

    <div
      id="mobile-navigation"
      class="mobile-menu"
      :class="{ open: isMenuOpen }"
    >
      <a
        v-for="section in sections"
        :key="section"
        href="#"
        class="mobile-link"
        :class="{ active: activeSection === section }"
        @click.prevent="selectSection(section)"
      >
        {{ section }}
      </a>

      <button class="mobile-login" type="button" @click="isMenuOpen = false">
        Login
      </button>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: relative;
  padding: 24px 5%;
}

.brand {
  color: #ffffff;
  font-size: 24px;
  font-weight: 700;
}

.nav-links {
  display: flex;
  align-items: center;
  gap: 32px;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
}

.nav-link {
  color: #ffffff;
  text-decoration: none;
  font-size: 18px;
  font-weight: 700;
  position: relative;
  padding: 8px 0;
  display: inline-block;

  transition: transform 0.25s ease;
}

.nav-link:not(.active):not(:hover) {
  -webkit-text-stroke: 0.35px #071a33;
  color: #ffffff;
}

.nav-link::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 2px;
  background-color: #d93645;

  transform: scaleX(0);
  transform-origin: center;
  transition: transform 0.25s ease;
}

.nav-link.active {
  font-weight: 700;
}

.nav-link.active::after {
  transform: scaleX(1);
}

.nav-link:hover {
  transform: translateY(-3px);
}
.login-button {
  background-color: #d93645;
  color: #ffffff;
  border: none;
  border-radius: 6px;
  padding: 10px 20px;
  font-size: 15px;
  cursor: pointer;
}
.login-button:hover {
  background-color: #c52c3b;
  transform: translateY(-3px);
}
.login-button:active {
  transform: translateY(0);
}

/* Hidden on desktop */
.menu-toggle,
.mobile-menu {
  display: none;
}

@media (max-width: 768px) {
  .navbar {
    padding: 22px 6%;
    position: relative;
    z-index: 10;
  }

  .brand {
    font-size: 32px;
  }

  /* Hide desktop navigation */
  .nav-links,
  .login-button {
    display: none;
  }

  /* Hamburger button */
  .menu-toggle {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 5px;

    width: 42px;
    height: 42px;
    padding: 8px;

    background: transparent;
    border: none;
    cursor: pointer;
  }

  .menu-toggle span {
    display: block;
    width: 26px;
    height: 2px;
    background-color: #ffffff;
    border-radius: 2px;
    transition:
      transform 0.25s ease,
      opacity 0.25s ease;
  }

  /* Hamburger transforms into X */
  .menu-toggle[aria-expanded="true"] span:nth-child(1) {
    transform: translateY(7px) rotate(45deg);
  }

  .menu-toggle[aria-expanded="true"] span:nth-child(2) {
    opacity: 0;
  }

  .menu-toggle[aria-expanded="true"] span:nth-child(3) {
    transform: translateY(-7px) rotate(-45deg);
  }

  /* Dropdown panel */
  .mobile-menu {
    display: flex;
    flex-direction: column;
    gap: 6px;

    position: absolute;
    top: calc(100% - 5px);
    left: 6%;
    right: 6%;

    padding: 16px;
    border-radius: 10px;

    background-color: rgba(7, 26, 51, 0.96);

    opacity: 0;
    visibility: hidden;
    transform: translateY(-10px);
    pointer-events: none;

    transition:
      opacity 0.25s ease,
      transform 0.25s ease,
      visibility 0.25s ease;
  }

  .mobile-menu.open {
    opacity: 1;
    visibility: visible;
    transform: translateY(0);
    pointer-events: auto;
  }

  .mobile-link {
    color: #ffffff;
    text-decoration: none;
    font-size: 16px;
    padding: 12px;
    border-radius: 6px;
    transition: background-color 0.2s ease;
  }

  .mobile-link:hover {
    background-color: rgba(255, 255, 255, 0.08);
  }

  .mobile-link.active {
    color: #ffffff;
    background-color: rgba(217, 54, 69, 0.2);
    border-left: 3px solid #d93645;
  }

  .mobile-login {
    margin-top: 8px;
    padding: 12px 20px;
    background-color: #d93645;
    color: #ffffff;
    border: none;
    border-radius: 6px;
    font-size: 16px;
    cursor: pointer;
  }

  .mobile-login:hover {
    background-color: #c52c3b;
  }
}
</style>
