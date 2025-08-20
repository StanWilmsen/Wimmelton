<script setup></script>

<template>
  <div id="app">
    <nav class="navbar">
      <div class="nav-container">
        <div class="logo">
          <div class="logo-icon">W</div>
          <span class="logo-text">Wimmelton</span>
        </div>
        <div class="nav-links">
          <router-link to="/" class="nav-link">Home</router-link>
          <router-link to="/diensten" class="nav-link">Diensten</router-link>
          <router-link to="/portfolio" class="nav-link">Portfolio</router-link>
          <router-link to="/contact" class="nav-link">Contact</router-link>
        </div>
        <div class="mobile-menu-toggle" @click="toggleMobileMenu">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>
    </nav>

    <div class="mobile-menu" :class="{ 'active': mobileMenuOpen }">
      <router-link to="/" class="mobile-nav-link" @click="closeMobileMenu">Home</router-link>
      <router-link to="/diensten" class="mobile-nav-link" @click="closeMobileMenu">Diensten</router-link>
      <router-link to="/portfolio" class="mobile-nav-link" @click="closeMobileMenu">Portfolio</router-link>
      <router-link to="/contact" class="mobile-nav-link" @click="closeMobileMenu">Contact</router-link>
    </div>

    <main class="main-content">
      <router-view />
    </main>

    <footer class="footer">
      <div class="footer-container">
        <div class="footer-section">
          <h3>Wimmelton</h3>
          <p>Data analyses en visualisaties die resultaten leveren</p>
        </div>
        <div class="footer-section">
          <h4>Contact</h4>
          <p>info@wimmelton.nl</p>
          <p>+31 6 12345678</p>
        </div>
        <div class="footer-section">
          <h4>Volg ons</h4>
          <div class="social-links">
            <a href="#" class="social-link">LinkedIn</a>
            <a href="#" class="social-link">Twitter</a>
          </div>
        </div>
      </div>
      <div class="footer-bottom">
        <p>&copy; 2024 Wimmelton. Alle rechten voorbehouden.</p>
      </div>
    </footer>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'App',
  setup() {
    const mobileMenuOpen = ref(false)

    const toggleMobileMenu = () => {
      mobileMenuOpen.value = !mobileMenuOpen.value
    }

    const closeMobileMenu = () => {
      mobileMenuOpen.value = false
    }

    return {
      mobileMenuOpen,
      toggleMobileMenu,
      closeMobileMenu
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  line-height: 1.6;
  color: #ffffff;
  background-color: #0a0a0a;
}

#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

/* Navbar */
.navbar {
  background-color: rgba(0, 0, 0, 0.95);
  backdrop-filter: blur(10px);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  border-bottom: 1px solid #333;
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 1rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.logo-icon {
  width: 40px;
  height: 40px;
  background: linear-gradient(135deg, #ffffff, #cccccc);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  font-weight: 700;
  color: #000;
  box-shadow: 0 4px 15px rgba(255, 255, 255, 0.2);
}

.logo-text {
  font-size: 1.5rem;
  font-weight: 700;
  background: linear-gradient(135deg, #ffffff, #cccccc);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.nav-links {
  display: flex;
  gap: 2rem;
}

.nav-link {
  color: #ffffff;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
  position: relative;
}

.nav-link:hover {
  color: #cccccc;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: linear-gradient(135deg, #ffffff, #cccccc);
  transition: width 0.3s ease;
}

.nav-link:hover::after {
  width: 100%;
}

.mobile-menu-toggle {
  display: none;
  flex-direction: column;
  cursor: pointer;
  gap: 4px;
}

.mobile-menu-toggle span {
  width: 25px;
  height: 3px;
  background-color: #ffffff;
  transition: 0.3s;
}

.mobile-menu {
  display: none;
  position: fixed;
  top: 80px;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.98);
  backdrop-filter: blur(10px);
  padding: 2rem;
  z-index: 999;
  transform: translateY(-100%);
  transition: transform 0.3s ease;
}

.mobile-menu.active {
  transform: translateY(0);
}

.mobile-nav-link {
  display: block;
  color: #ffffff;
  text-decoration: none;
  font-size: 1.2rem;
  padding: 1rem 0;
  border-bottom: 1px solid #333;
  transition: color 0.3s ease;
}

.mobile-nav-link:hover {
  color: #cccccc;
}

/* Main Content */
.main-content {
  flex: 1;
  margin-top: 80px;
}

/* Footer */
.footer {
  background-color: #000000;
  border-top: 1px solid #333;
  margin-top: auto;
}

.footer-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 3rem 2rem;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.footer-section h3 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  background: linear-gradient(135deg, #ffffff, #cccccc);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.footer-section h4 {
  font-size: 1.2rem;
  margin-bottom: 1rem;
  color: #ffffff;
}

.footer-section p {
  color: #cccccc;
  margin-bottom: 0.5rem;
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-link {
  color: #cccccc;
  text-decoration: none;
  transition: color 0.3s ease;
}

.social-link:hover {
  color: #ffffff;
}

.footer-bottom {
  border-top: 1px solid #333;
  padding: 1.5rem 2rem;
  text-align: center;
}

.footer-bottom p {
  color: #666;
}

/* Responsive Design */
@media (max-width: 768px) {
  .nav-links {
    display: none;
  }
  
  .mobile-menu-toggle {
    display: flex;
  }
  
  .mobile-menu {
    display: block;
  }
  
  .nav-container {
    padding: 1rem;
  }
  
  .footer-container {
    padding: 2rem 1rem;
  }
}

/* Utility Classes */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.btn {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  background: linear-gradient(135deg, #ffffff, #cccccc);
  color: #000000;
  text-decoration: none;
  border-radius: 8px;
  font-weight: 600;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
}

.btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(255, 255, 255, 0.3);
}

.btn-secondary {
  background: transparent;
  color: #ffffff;
  border: 2px solid #ffffff;
}

.btn-secondary:hover {
  background: #ffffff;
  color: #000000;
}

.section {
  padding: 5rem 0;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 700;
  text-align: center;
  margin-bottom: 1rem;
  background: linear-gradient(135deg, #ffffff, #cccccc);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.section-subtitle {
  font-size: 1.2rem;
  text-align: center;
  color: #cccccc;
  margin-bottom: 3rem;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.card {
  background-color: rgba(255, 255, 255, 0.05);
  border: 1px solid #333;
  border-radius: 12px;
  padding: 2rem;
  transition: all 0.3s ease;
}

.card:hover {
  transform: translateY(-5px);
  border-color: #ffffff;
  box-shadow: 0 10px 30px rgba(255, 255, 255, 0.1);
}

.grid {
  display: grid;
  gap: 2rem;
}

.grid-2 {
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
}

.grid-3 {
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
}

.text-center {
  text-align: center;
}

.mb-1 { margin-bottom: 0.5rem; }
.mb-2 { margin-bottom: 1rem; }
.mb-3 { margin-bottom: 1.5rem; }
.mb-4 { margin-bottom: 2rem; }
.mb-5 { margin-bottom: 3rem; }

.mt-1 { margin-top: 0.5rem; }
.mt-2 { margin-top: 1rem; }
.mt-3 { margin-top: 1.5rem; }
.mt-4 { margin-top: 2rem; }
.mt-5 { margin-top: 3rem; }
</style>
