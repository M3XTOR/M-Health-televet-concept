<script setup>
import { ref, computed } from 'vue'

const tips = [
  {
    category: 'DOG CARE',
    title: 'Keeping Your Dog Healthy and Active',
    date: '2026-10-11',
    preview:
      "Regular exercise, balanced nutrition, and routine grooming all contribute to your dog's overall wellbeing. However, the amount of exercise your dog needs can depend on its age, breed, and health condition. Understanding these differences can help you..."
  },
  {
    category: 'CAT CARE',
    title: 'Simple Ways to Keep Your Cat Healthy',
    date: '2026-10-10',
    preview:
      'Cats benefit from clean drinking water, appropriate nutrition, regular veterinary checkups, and an environment that encourages natural behaviours. Changes in appetite, grooming habits, or energy levels may also indicate that...'
  },
  {
    category: 'LIVESTOCK CARE',
    title: 'Protecting Your Livestock From Common Diseases',
    date: '2026-10-09',
    preview:
      'Keeping animal housing clean, providing adequate nutrition, and following appropriate vaccination schedules can help reduce disease risks in livestock. Farmers should also watch for early warning signs such as...'
  },
  {
    category: 'BIRD CARE',
    title: 'Creating a Healthy Environment for Your Birds',
    date: '2026-10-08',
    preview:
      'Birds need suitable housing, clean water, proper nutrition, and enough space to move comfortably. Maintaining good hygiene and monitoring changes in behaviour are important because some birds may hide signs of illness until...'
  }
]

const currentIndex = ref(0)
const currentTip = computed(() => tips[currentIndex.value])

function nextTip() {
  currentIndex.value = (currentIndex.value + 1) % tips.length
}

function previousTip() {
  currentIndex.value = (currentIndex.value - 1 + tips.length) % tips.length
}
</script>

<template>
  <section id="animal-care-tips" class="latest-tips">
    <div class="tips-container">
      <div class="tips-heading">
        <span class="eyebrow">ANIMAL CARE INSIGHTS</span>
        <h2>Little Tips. Healthier Animals.</h2>
        <p>
          Discover practical animal-care advice to help you make
          better decisions for the animals you care for.
        </p>
      </div>

      <div class="tips-layout">
        <div class="tips-image">
          <img
            src="/images/animal-care.jpg"
            alt="A variety of healthy domestic animals"
            loading="lazy"
          />
          <div class="image-badge">
            <span>ANIMAL CARE</span>
            <strong>DAILY INSIGHT</strong>
          </div>
        </div>

        <div class="tips-content">
          <Transition name="tip-fade" mode="out-in">
            <div :key="currentIndex" class="tip-details">
              <span class="tip-category">{{ currentTip.category }}</span>
              <h3>{{ currentTip.title }}</h3>
              <p class="tip-preview">{{ currentTip.preview }}</p>

              <div class="tip-date">
                <svg
                  width="17"
                  height="17"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="1.8"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  aria-hidden="true"
                >
                  <rect x="3" y="5" width="18" height="16" rx="2" />
                  <path d="M16 3v4M8 3v4M3 10h18" />
                </svg>
                <span>{{ currentTip.date }}</span>
              </div>

              <span class="read-full">
                Read Full Tip
                <span aria-hidden="true">↗</span>
              </span>
            </div>
          </Transition>

          <div class="tip-navigation">
            <span class="tip-counter">
              {{ String(currentIndex + 1).padStart(2, '0') }}
              <span class="counter-divider">/</span>
              {{ String(tips.length).padStart(2, '0') }}
            </span>

            <div class="navigation-buttons">
              <button
                type="button"
                class="nav-arrow"
                aria-label="Previous tip"
                @click="previousTip"
              >
                ←
              </button>

              <button
                type="button"
                class="nav-arrow"
                aria-label="Next tip"
                @click="nextTip"
              >
                →
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.latest-tips {
  background: #fcfcfc;
  padding: 100px 6%;
}

.tips-container {
  max-width: 1280px;
  margin: 0 auto;
}

.tips-heading {
  max-width: 720px;
  margin: 0 auto 60px;
  text-align: center;
}

.eyebrow {
  display: inline-block;
  color: #d93645;
  font-size: 12px;
  font-weight: 800;
  letter-spacing: 2px;
  margin-bottom: 16px;
}

.tips-heading h2 {
  color: #071a33;
  font-size: clamp(30px, 4vw, 46px);
  font-weight: 800;
  line-height: 1.2;
  letter-spacing: -1.5px;
  margin: 0 0 18px;
}

.tips-heading p {
  color: #5b6b7c;
  font-size: 15px;
  line-height: 1.8;
  margin: 0;
}

.tips-layout {
  display: grid;
  grid-template-columns: 45% minmax(0, 1fr);
  gap: 65px;
  align-items: center;
}

.tips-image {
  position: relative;
  height: 480px;
  border-radius: 22px;
  overflow: hidden;
}

.tips-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.image-badge {
  position: absolute;
  bottom: 22px;
  left: 22px;
  display: flex;
  flex-direction: column;
  gap: 5px;
  padding: 13px 17px;
  background: rgba(7, 26, 51, 0.92);
  color: white;
  border-radius: 12px;
}

.image-badge span {
  font-size: 10px;
  letter-spacing: 1.5px;
}

.image-badge strong {
  font-size: 12px;
  letter-spacing: 0.5px;
}

.tips-content {
  min-width: 0;
}

.tip-details {
  min-height: 340px;
}

.tip-category {
  color: #d93645;
  font-size: 12px;
  font-weight: 800;
  letter-spacing: 1.5px;
}

.tip-details h3 {
  color: #071a33;
  font-size: clamp(25px, 3vw, 37px);
  line-height: 1.3;
  letter-spacing: -1px;
  margin: 18px 0;
}

.tip-preview {
  color: #5b6b7c;
  font-size: 15px;
  line-height: 1.9;
  margin: 0 0 24px;
}

.tip-date {
  display: flex;
  align-items: center;
  gap: 9px;
  color: #7b8998;
  font-size: 13px;
  margin-bottom: 24px;
}

.read-full {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  color: #d93645;
  font-size: 14px;
  font-weight: 800;
  border-bottom: 1px solid #d93645;
  padding-bottom: 5px;
}

.tip-navigation {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
  border-top: 1px solid #e4e9ee;
  padding-top: 24px;
  margin-top: 25px;
}

.tip-counter {
  color: #071a33;
  font-size: 19px;
  font-weight: 800;
}

.counter-divider {
  color: #9ba7b3;
  margin: 0 9px;
}

.navigation-buttons {
  display: flex;
  gap: 12px;
}

.nav-arrow {
  width: 44px;
  height: 44px;
  border: 1px solid #dce3e9;
  border-radius: 50%;
  background: transparent;
  color: #071a33;
  font-size: 19px;
  cursor: pointer;
  transition: all 0.25s ease;
}

.nav-arrow:hover {
  background: #d93645;
  border-color: #d93645;
  color: white;
}

/* Tip transition */

.tip-fade-enter-active,
.tip-fade-leave-active {
  transition: opacity 0.2s ease, transform 0.2s ease;
}

.tip-fade-enter-from {
  opacity: 0;
  transform: translateY(10px);
}

.tip-fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}

/* Tablet */

@media (max-width: 1024px) {
  .tips-layout {
    gap: 35px;
  }

  .tips-image {
    height: 420px;
  }
}

/* Mobile */

@media (max-width: 768px) {
  .latest-tips {
    padding: 75px 5%;
  }

  .tips-heading {
    margin-bottom: 40px;
  }

  .tips-heading h2 {
    letter-spacing: -0.8px;
  }

  .tips-layout {
    grid-template-columns: 1fr;
    gap: 35px;
  }

  .tips-image {
    height: 340px;
  }

  .tip-details {
    min-height: 0;
  }

  .tip-details h3 {
    font-size: 27px;
  }

  .tip-preview {
    font-size: 14px;
  }

  .tip-navigation {
    margin-top: 30px;
  }
}

@media (max-width: 480px) {
  .tips-image {
    height: 280px;
  }

  .image-badge {
    bottom: 15px;
    left: 15px;
  }
}

@media (prefers-reduced-motion: reduce) {
  .tip-fade-enter-active,
  .tip-fade-leave-active,
  .nav-arrow {
    transition: none;
  }
}
</style>