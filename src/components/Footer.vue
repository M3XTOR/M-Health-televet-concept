<template>
  <footer class="site-footer">
    <div class="footer-container">
      <div class="footer-grid">

        <!-- Brand -->
        <div class="footer-brand">
          <h2>M-Health <span>TeleVet</span></h2>
          <p>
            Practical animal healthcare information for pet owners
            and livestock farmers across Nigeria.
          </p>
        </div>

        <!-- Navigation -->
        <div class="footer-navigation">
          <h3>Quick Links</h3>

          <nav aria-label="Footer navigation">
            <a href="#top">Home</a>
            <a href="#animal-care-tips">Today's Tips</a>
            <span class="footer-placeholder">Today's Trivia</span>
            <span class="footer-placeholder">Expert Profiles</span>
          </nav>
        </div>

        <!-- Subscription -->
        <div class="footer-subscribe">
          <h3>Stay Informed</h3>

          <p>
            Explore helpful animal-care content with flexible
            subscription options.
          </p>

          <div class="ussd-box">
            <div class="ussd-icon">
              <svg
                width="22"
                height="22"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="1.8"
                stroke-linecap="round"
                stroke-linejoin="round"
                aria-hidden="true"
              >
                <rect x="6" y="2" width="12" height="20" rx="2" />
                <path d="M11 18h2" />
              </svg>
            </div>

            <div class="ussd-details">
              <span>SUBSCRIBE VIA USSD</span>
              <strong>*20790#</strong>
            </div>
          </div>

          <a href="#subscription-plans" class="footer-plan-link">
            View Subscription Plans
            <span aria-hidden="true">↗</span>
          </a>
        </div>

      </div>

      <div class="footer-bottom">
        <p>© 2026 M-Health TeleVet. All rights reserved.</p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.site-footer {
  background: #071a33;
  color: #ffffff;
  padding: 85px 6% 0;
}

.footer-container {
  max-width: 1280px;
  margin: 0 auto;
}

.footer-grid {
  display: grid;
  grid-template-columns: 1.3fr 0.8fr 1fr;
  gap: 75px;
  padding-bottom: 75px;
}

/* Brand */

.footer-brand h2 {
  position: relative;
  color: #ffffff;
  font-size: clamp(27px, 3vw, 36px);
  font-weight: 800;
  line-height: 1.25;
  letter-spacing: -1.3px;
  margin: 0 0 25px;
  padding-left: 17px;
}

.footer-brand h2::before {
  content: "";
  position: absolute;
  left: 0;
  top: 5px;
  width: 4px;
  height: 36px;
  border-radius: 4px;
  background: #d93645;
}

.footer-brand h2 span {
  color: #ffffff;
}

.footer-brand p {
  max-width: 330px;
  color: #b7c5d4;
  font-size: 14px;
  line-height: 1.9;
  margin: 0;
}

/* Shared headings */

.footer-navigation h3,
.footer-subscribe h3 {
  color: #ffffff;
  font-size: 19px;
  font-weight: 800;
  margin: 5px 0 28px;
  padding-bottom: 15px;
  position: relative;
}

.footer-navigation h3::after,
.footer-subscribe h3::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  width: 43px;
  height: 3px;
  border-radius: 3px;
  background: #d93645;
}

/* Navigation */

.footer-navigation nav {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 17px;
}

.footer-navigation a,
.footer-placeholder {
  color: #b7c5d4;
  font-size: 14px;
  text-decoration: none;
}

.footer-navigation a {
  transition: color 0.25s ease, transform 0.25s ease;
}

.footer-navigation a:hover {
  color: #d93645;
  transform: translateX(6px);
}

.footer-placeholder {
  cursor: default;
}

/* Subscription */

.footer-subscribe > p {
  color: #b7c5d4;
  font-size: 14px;
  line-height: 1.9;
  margin: 0 0 23px;
}

.ussd-box {
  display: flex;
  align-items: center;
  gap: 15px;
  padding: 18px 20px;
  border: 1px solid rgba(255, 255, 255, 0.14);
  border-radius: 13px;
  background: rgba(255, 255, 255, 0.055);
}

.ussd-icon {
  width: 45px;
  height: 45px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  border-radius: 11px;
  color: #ffffff;
  background: #d93645;
}

.ussd-details {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.ussd-details span {
  color: #b7c5d4;
  font-size: 10px;
  font-weight: 700;
  letter-spacing: 1.2px;
}

.ussd-details strong {
  color: #ffffff;
  font-size: 23px;
  font-weight: 800;
  letter-spacing: 1px;
}

.footer-plan-link {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  margin-top: 22px;
  color: #ffffff;
  font-size: 13px;
  font-weight: 700;
  text-decoration: none;
  transition: color 0.25s ease, gap 0.25s ease;
}

.footer-plan-link:hover {
  color: #d93645;
  gap: 13px;
}

/* Copyright */

.footer-bottom {
  border-top: 1px solid rgba(255, 255, 255, 0.12);
  padding: 25px 0;
  text-align: center;
}

.footer-bottom p {
  color: #8fa1b5;
  font-size: 12px;
  margin: 0;
}

/* Tablet */

@media (max-width: 1024px) {
  .footer-grid {
    gap: 40px;
  }
}

/* Mobile */

@media (max-width: 768px) {
  .site-footer {
    padding: 65px 5% 0;
  }

  .footer-grid {
    grid-template-columns: 1fr;
    gap: 45px;
    padding-bottom: 55px;
  }

  .footer-brand h2 {
    font-size: 30px;
  }

  .footer-brand p {
    max-width: 400px;
  }

  .footer-navigation h3,
  .footer-subscribe h3 {
    margin-bottom: 23px;
  }

  .footer-subscribe {
    max-width: 420px;
  }

  .footer-bottom {
    padding: 23px 0;
  }
}

@media (prefers-reduced-motion: reduce) {
  .footer-navigation a,
  .footer-plan-link {
    transition: none;
  }
}
</style>