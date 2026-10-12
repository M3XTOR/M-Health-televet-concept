<script setup>
const animals = [
  {
    name: 'Cats',
    image: '/images/animals/cat.svg',
    description: 'Good nutrition and regular care support healthy, active cats.'
  },
  {
    name: 'Dogs',
    image: '/images/animals/dog.svg',
    description: 'Exercise, vaccination, and proper feeding support your dog’s wellbeing.'
  },
  {
    name: 'Birds',
    image: '/images/animals/bird.svg',
    description: 'Clean housing and balanced feeding help birds stay healthy.'
  },
  {
    name: 'Fish',
    image: '/images/animals/fish.svg',
    description: 'Clean water and proper feeding are essential for healthy fish.'
  },
  {
    name: 'Cattle',
    image: '/images/animals/cattle.svg',
    description: 'Good nutrition and preventive care support healthier cattle.'
  },
  {
    name: 'Sheep',
    image: '/images/animals/sheep.svg',
    description: 'Proper feeding, hygiene, and routine care help sheep thrive.'
  }
]
</script>

<template>
  <section class="introduction">
    <div class="intro-container">

      <!-- Left: Animal Cards -->
      <div class="animal-grid">
        <article
          v-for="animal in animals"
          :key="animal.name"
          class="animal-card"
        >
          <img
            :src="animal.image"
            :alt="`${animal.name} illustration`"
            class="animal-art"
            loading="lazy"
          />

          <div class="animal-details">
            <h3>{{ animal.name }}</h3>
            <p>{{ animal.description }}</p>
          </div>
        </article>
      </div>

      <!-- Right: Introduction -->
      <div class="intro-content">
        <span class="intro-label">ABOUT M-HEALTH TELEVET</span>

        <h2>Better Animal Care Starts With Better Information.</h2>

        <p>
          M-Health TeleVet brings practical animal-care knowledge
          closer to you. From everyday nutrition and vaccination
          advice to disease prevention and expert insights, we help
          animal owners make more informed decisions.
        </p>

        <p>
          Whether you're caring for a beloved pet or managing
          livestock, discover helpful information designed to
          support healthier animals and more confident care.
        </p>
      </div>

    </div>
  </section>
</template>

<style scoped>
.introduction {
  background-color: #fcfcfc;
  padding: 100px 6%;
}

.intro-container {
  max-width: 1280px;
  margin: 0 auto;

  display: grid;
  grid-template-columns: 1.2fr 1fr;
  gap: 60px;
  align-items: center;
}

/* Animal cards */

.animal-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 16px;
}

.animal-card {
  background-color: #ffffff;
  border: 1px solid #e5eaf0;
  border-radius: 14px;
  overflow: hidden;

  transition: transform 0.25s ease, box-shadow 0.25s ease;
}

.animal-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 24px rgba(7, 26, 51, 0.1);
}

.animal-art {
  display: block;
  width: 100%;
  aspect-ratio: 3 / 2;
  object-fit: cover;
}

.animal-details {
  padding: 12px;
}

.animal-details h3 {
  color: #071a33;
  font-size: 15px;
  font-weight: 700;
  margin: 0 0 6px;
}

.animal-details p {
  color: #64748b;
  font-size: 12px;
  line-height: 1.5;
  margin: 0;
}

/* Introduction text panel */

.intro-content {
  background-color: #f3f6fa;
  padding: 40px;
  border-radius: 20px;
  border: 1px solid #e5eaf0;
}

.intro-label {
  display: inline-block;
  color: #d93645;
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 1.5px;
  margin-bottom: 20px;
}

.intro-content h2 {
  color: #071a33;
  font-size: clamp(28px, 2.8vw, 38px);
  line-height: 1.2;
  margin: 0 0 24px;
}

.intro-content p {
  color: #475569;
  font-size: 15px;
  line-height: 1.8;
  margin-bottom: 18px;
}

/* Tablet */

@media (max-width: 1024px) {
  .intro-container {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .intro-content {
    padding: 32px;
  }
}

/* Mobile */

@media (max-width: 600px) {
  .introduction {
    padding: 65px 5%;
  }

  .animal-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 12px;
  }

  .intro-content {
    padding: 26px;
  }

  .intro-content h2 {
    font-size: 28px;
  }

  .animal-details p {
    font-size: 11px;
  }
}
</style>