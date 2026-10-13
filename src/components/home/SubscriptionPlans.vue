<script setup>
const plans = [
  {
    name: "Daily",
    price: "100",
    duration: "day",
    description: "Enjoy M-Health TeleVet content for 24 hours.",
    period: "1 day",
  },
  {
    name: "Weekly",
    price: "300",
    duration: "7 days",
    description: "Stay informed with animal-care content throughout the week.",
    period: "7 days",
  },
  {
    name: "Monthly",
    price: "500",
    duration: "30 days",
    description: "Get continued access to helpful animal-care information.",
    period: "30 days",
  },
];
</script>

<template>
  <section class="subscription-section" id="subscription-plans">
    <div class="subscription-container">
      <!-- Section heading -->
      <div class="section-heading">
        <span class="eyebrow">OUR PLANS</span>

        <h2>Flexible Plans for Better Animal Care</h2>

        <p>
          Choose a subscription that works for you. Access M-Health TeleVet
          content with flexible daily, weekly, and monthly options.
        </p>
      </div>

      <!-- Pricing cards -->
      <div class="pricing-grid">
        <article v-for="plan in plans" :key="plan.name" class="pricing-card">
          <div class="plan-header">
            <span class="plan-name">{{ plan.name }} Plan</span>
            <span class="plan-period">{{ plan.period }}</span>
          </div>

          <div class="plan-price">
            <span class="currency">₦</span>
            <span class="amount">{{ plan.price }}</span>
            <span class="duration">/ {{ plan.duration }}</span>
          </div>

          <p class="plan-description">
            {{ plan.description }}
          </p>

          <div class="card-divider"></div>

          <p class="options-heading">Available options</p>

          <div class="subscription-option">
            <span class="option-icon">✓</span>
            <div>
              <strong>One-Time</strong>
              <small>Subscribe once for the selected period.</small>
            </div>
          </div>

          <div class="subscription-option">
            <span class="option-icon">✓</span>
            <div>
              <strong>Auto-Renewal</strong>
              <small>Automatically renew when your plan expires.</small>
            </div>
          </div>
        </article>
      </div>

      <!-- USSD subscription panel -->
      <div class="ussd-panel">
        <div class="ussd-information">
          <span class="ussd-eyebrow">READY TO SUBSCRIBE?</span>

          <h3>Get Started From Your Phone</h3>

          <p>
            Dial the USSD code provided to explore the available M-Health
            TeleVet subscription options.
          </p>
        </div>

        <div class="ussd-action">
          <span class="ussd-label">SUBSCRIPTION CODE</span>

          <span class="ussd-code">*20790#</span>

          <!-- Visible on mobile only -->
          <a
            href="tel:*20790%23"
            class="dial-link"
            aria-label="Open phone dialer with USSD code *20790#"
          >
            Dial Code
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="17"
              height="17"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
              aria-hidden="true"
            >
              <path
                d="M22 16.92v3a2 2 0 0 1-2.18 2A19.79 19.79 0 0 1 3.09 5.18 2 2 0 0 1 5.08 3h3a2 2 0 0 1 2 1.72c.12.96.34 1.9.65 2.8a2 2 0 0 1-.45 2.11L8.91 11a16 16 0 0 0 4.09 4.09l1.37-1.37a2 2 0 0 1 2.11-.45c.9.31 1.84.53 2.8.65A2 2 0 0 1 22 16.92z"
              />
            </svg>
          </a>
        </div>
      </div>

      <p class="subscription-note">
        Subscription charges apply. Auto-renewal plans renew automatically
        unless cancelled according to the provider's terms.
      </p>
    </div>
  </section>
</template>

<style scoped>
.subscription-section {
  background: #edf4f8;
  padding: 100px 6%;
}

.subscription-container {
  max-width: 1280px;
  margin: 0 auto;
}

/* Section heading */

.section-heading {
  max-width: 700px;
  margin: 0 auto 55px;
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

.section-heading h2 {
  color: #071a33;
  font-size: clamp(30px, 4vw, 46px);
  font-weight: 800;
  line-height: 1.2;
  letter-spacing: -1.5px;
  margin: 0 0 18px;
}

.section-heading p {
  color: #5b6b7c;
  font-size: 15px;
  line-height: 1.8;
  margin: 0;
}

/* Pricing cards */

.pricing-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 24px;
}

.pricing-card {
  background: #ffffff;
  border: 1px solid #e0e8ef;
  border-radius: 20px;
  padding: 32px 28px;
  box-shadow: 0 8px 28px rgba(7, 26, 51, 0.035);
  transition:
    transform 0.3s ease,
    box-shadow 0.3s ease;
}

.pricing-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 16px 36px rgba(7, 26, 51, 0.09);
}

.plan-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 12px;
}

.plan-name {
  color: #071a33;
  font-size: 17px;
  font-weight: 800;
}

.plan-period {
  color: #0c857b;
  background: #e6f7f3;
  font-size: 11px;
  font-weight: 700;
  padding: 7px 11px;
  border-radius: 30px;
  white-space: nowrap;
}

.plan-price {
  display: flex;
  align-items: baseline;
  gap: 2px;
  margin: 30px 0 18px;
  color: #071a33;
}

.currency {
  font-size: 25px;
  font-weight: 700;
  align-self: flex-start;
  margin-top: 9px;
}

.amount {
  font-size: clamp(45px, 4vw, 58px);
  font-weight: 800;
  letter-spacing: -2px;
  line-height: 1;
}

.duration {
  font-size: 13px;
  font-weight: 500;
  color: #718093;
  margin-left: 6px;
}

.plan-description {
  color: #667587;
  font-size: 13px;
  line-height: 1.8;
  min-height: 48px;
  margin: 0;
}

.card-divider {
  height: 1px;
  background: #e9eef2;
  margin: 26px 0 23px;
}

.options-heading {
  color: #071a33;
  font-size: 12px;
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: 0.7px;
  margin: 0 0 20px;
}

.subscription-option {
  display: flex;
  align-items: flex-start;
  gap: 12px;
  margin-bottom: 20px;
}

.subscription-option:last-child {
  margin-bottom: 0;
}

.option-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  width: 22px;
  height: 22px;
  border-radius: 50%;
  background: #e6f7f3;
  color: #0c857b;
  font-size: 12px;
  font-weight: 800;
}

.subscription-option strong {
  display: block;
  color: #071a33;
  font-size: 13px;
  font-weight: 700;
  margin-bottom: 5px;
}

.subscription-option small {
  display: block;
  color: #778596;
  font-size: 12px;
  line-height: 1.6;
}

/* USSD panel */

.ussd-panel {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 40px;
  background: #071a33;
  border-radius: 22px;
  padding: 42px 48px;
  margin-top: 45px;
}

.ussd-information {
  max-width: 560px;
}

.ussd-eyebrow {
  color: #64d6c8;
  font-size: 11px;
  font-weight: 800;
  letter-spacing: 1.8px;
}

.ussd-information h3 {
  color: #ffffff;
  font-size: clamp(23px, 3vw, 30px);
  font-weight: 800;
  margin: 12px 0;
}

.ussd-information p {
  color: #b7c5d5;
  font-size: 13px;
  line-height: 1.8;
  margin: 0;
}

.ussd-action {
  display: flex;
  flex-direction: column;
  align-items: center;
  flex-shrink: 0;
  gap: 10px;
  background: rgba(255, 255, 255, 0.07);
  border: 1px solid rgba(255, 255, 255, 0.12);
  border-radius: 16px;
  padding: 20px 35px;
}

.ussd-label {
  color: #a8bacd;
  font-size: 10px;
  font-weight: 700;
  letter-spacing: 1.5px;
}

.ussd-code {
  color: #ffffff;
  font-size: 30px;
  font-weight: 800;
  letter-spacing: 1px;
  white-space: nowrap;
}

/* Hidden on desktop */

.dial-link {
  display: none;
}

.subscription-note {
  color: #758495;
  font-size: 11px;
  line-height: 1.7;
  text-align: center;
  margin: 20px auto 0;
}

/* Tablet */

@media (max-width: 1024px) {
  .pricing-grid {
    gap: 16px;
  }

  .pricing-card {
    padding: 28px 20px;
  }

  .ussd-panel {
    padding: 35px;
    gap: 25px;
  }
}

/* Mobile */

@media (max-width: 768px) {
  .subscription-section {
    padding: 75px 5%;
  }

  .section-heading {
    margin-bottom: 38px;
  }

  .section-heading h2 {
    letter-spacing: -0.8px;
  }

  .pricing-grid {
    grid-template-columns: 1fr;
    gap: 18px;
  }

  .pricing-card {
    padding: 28px 25px;
  }

  .plan-description {
    min-height: auto;
  }

  .ussd-panel {
    flex-direction: column;
    align-items: stretch;
    padding: 30px 24px;
    margin-top: 35px;
    gap: 25px;
  }

  .ussd-action {
    width: 100%;
    box-sizing: border-box;
    padding: 22px 15px;
  }

  .ussd-code {
    font-size: 32px;
  }

  /* Show dial link on mobile */

  .dial-link {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    background: #d93645;
    color: #ffffff;
    text-decoration: none;
    font-size: 13px;
    font-weight: 800;
    border-radius: 9px;
    padding: 12px 24px;
    margin-top: 8px;
    transition: background 0.2s ease;
  }

  .dial-link:hover {
    background: #bf2938;
  }
}

@media (prefers-reduced-motion: reduce) {
  .pricing-card,
  .dial-link {
    transition: none;
  }
}
</style>
