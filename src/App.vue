<script setup></script>

<template>
  <div id="app">
    <!-- Navigation -->
    <nav class="navbar" :class="{ 'scrolled': isScrolled }">
      <div class="nav-container">
        <div class="logo">
          <div class="logo-icon">W</div>
          <span class="logo-text">Wimmelton</span>
        </div>
        <div class="nav-links">
          <a href="#home" class="nav-link">Home</a>
          <a href="#services" class="nav-link">Diensten</a>
          <a href="#portfolio" class="nav-link">Portfolio</a>
          <a href="#contact" class="nav-link">Contact</a>
        </div>
        <div class="mobile-menu-toggle" @click="toggleMobileMenu">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>
    </nav>

    <!-- Mobile Menu -->
    <div class="mobile-menu" :class="{ 'active': mobileMenuOpen }">
      <a href="#home" class="mobile-nav-link" @click="closeMobileMenu">Home</a>
      <a href="#services" class="mobile-nav-link" @click="closeMobileMenu">Diensten</a>
      <a href="#portfolio" class="mobile-nav-link" @click="closeMobileMenu">Portfolio</a>
      <a href="#contact" class="mobile-nav-link" @click="closeMobileMenu">Contact</a>
    </div>

    <!-- Hero Section -->
    <section id="home" class="hero">
      <div class="hero-background">
        <div class="floating-shapes">
          <div class="shape shape-1"></div>
          <div class="shape shape-2"></div>
          <div class="shape shape-3"></div>
          <div class="shape shape-4"></div>
        </div>
        <div class="gradient-overlay"></div>
      </div>
      
      <div class="container">
        <div class="hero-content">
          <h1 class="hero-title">
            <span class="title-line">Data Analyses</span>
            <span class="title-line">& Visualisaties</span>
            <span class="title-accent">die resultaten leveren</span>
          </h1>
          <p class="hero-description">
            Wimmelton transformeert complexe data in heldere inzichten. 
            Wij maken data toegankelijk, begrijpelijk en actiegericht.
          </p>
          <div class="hero-buttons">
            <a href="#services" class="btn btn-primary">Ontdek onze diensten</a>
            <a href="#contact" class="btn btn-secondary">Neem contact op</a>
          </div>
        </div>
        
        <div class="hero-visual">
          <div class="data-orb">
            <div class="orb-core"></div>
            <div class="orb-ring orb-ring-1"></div>
            <div class="orb-ring orb-ring-2"></div>
            <div class="orb-ring orb-ring-3"></div>
            <div class="data-points">
              <div class="data-point" v-for="i in 8" :key="i"></div>
            </div>
          </div>
        </div>
      </div>
      
      <div class="scroll-indicator">
        <div class="scroll-arrow"></div>
      </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="services">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Onze Diensten</h2>
          <p class="section-subtitle">
            Van data-analyse tot implementatie - wij bieden end-to-end oplossingen
          </p>
        </div>
        
        <div class="services-grid">
          <div class="service-card" v-for="(service, index) in services" :key="index">
            <div class="service-icon">
              <div class="icon-bg"></div>
              <span class="icon-emoji">{{ service.icon }}</span>
            </div>
            <h3>{{ service.title }}</h3>
            <p>{{ service.description }}</p>
            <ul class="service-features">
              <li v-for="feature in service.features" :key="feature">{{ feature }}</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- Portfolio Section -->
    <section id="portfolio" class="portfolio">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Portfolio</h2>
          <p class="section-subtitle">
            Bekijk enkele van onze succesvolle projecten
          </p>
        </div>
        
        <div class="portfolio-grid">
          <div class="portfolio-item" v-for="(project, index) in projects" :key="index">
            <div class="portfolio-image">
              <div class="image-placeholder">
                <div class="chart-preview">
                  <div class="chart-bar" v-for="i in 5" :key="i" :style="{ height: Math.random() * 80 + 20 + '%' }"></div>
                </div>
              </div>
            </div>
            <div class="portfolio-content">
              <h3>{{ project.title }}</h3>
              <p>{{ project.description }}</p>
              <div class="portfolio-tags">
                <span v-for="tag in project.tags" :key="tag" class="tag">{{ tag }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Contact</h2>
          <p class="section-subtitle">
            Klaar om uw data te laten werken? Neem contact op
          </p>
        </div>
        
        <div class="contact-content">
          <div class="contact-form">
            <form @submit.prevent="submitForm">
              <div class="form-group">
                <input type="text" v-model="form.name" required placeholder="Naam">
              </div>
              <div class="form-group">
                <input type="email" v-model="form.email" required placeholder="E-mail">
              </div>
              <div class="form-group">
                <textarea v-model="form.message" required placeholder="Bericht" rows="5"></textarea>
              </div>
              <button type="submit" class="btn btn-primary" :disabled="isSubmitting">
                {{ isSubmitting ? 'Versturen...' : 'Verstuur bericht' }}
              </button>
            </form>
          </div>
          
          <div class="contact-info">
            <div class="contact-method">
              <div class="method-icon">📧</div>
              <div>
                <h3>E-mail</h3>
                <p>info@wimmelton.nl</p>
              </div>
            </div>
            <div class="contact-method">
              <div class="method-icon">📱</div>
              <div>
                <h3>Telefoon</h3>
                <p>+31 6 12345678</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <div class="container">
        <div class="footer-content">
          <div class="footer-logo">
            <div class="logo-icon">W</div>
            <span class="logo-text">Wimmelton</span>
          </div>
          <p>&copy; 2024 Wimmelton. Alle rechten voorbehouden.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import { ref, onMounted, onUnmounted } from 'vue'

export default {
  name: 'App',
  setup() {
    const mobileMenuOpen = ref(false)
    const isScrolled = ref(false)
    const isSubmitting = ref(false)

    const services = [
      {
        icon: '📊',
        title: 'Data Analyse & BI',
        description: 'Diepgaande analyses van uw bedrijfsdata om trends en kansen te identificeren.',
        features: ['KPI dashboards', 'Trend analyses', 'Predictive analytics', 'Performance monitoring']
      },
      {
        icon: '🎨',
        title: 'Data Visualisatie',
        description: 'Complexe data omzetten in heldere, overtuigende visualisaties.',
        features: ['Interactieve dashboards', 'Infographics', 'Presentatie slides', 'Real-time monitoring']
      },
      {
        icon: '🔍',
        title: 'Data Auditing',
        description: 'Beoordeling van uw data-infrastructuur en -kwaliteit.',
        features: ['Data kwaliteitscontrole', 'Infrastructuur audit', 'Compliance check', 'Verbeteringsplan']
      },
      {
        icon: '🚀',
        title: 'Implementatie',
        description: 'Implementeren van data-gedreven processen en team training.',
        features: ['Proces implementatie', 'Team training', 'Change management', 'Ondersteuning']
      }
    ]

    const projects = [
      {
        title: 'Retail Dashboard',
        description: 'Compleet dashboard voor retail keten met real-time KPI monitoring',
        tags: ['Dashboard', 'Retail', 'KPI']
      },
      {
        title: 'Financial Analysis',
        description: 'Diepgaande analyse van financiële data voor investeringsbeslissingen',
        tags: ['Financiën', 'Analyse', 'Investeringen']
      },
      {
        title: 'Marketing Analytics',
        description: 'Comprehensive analyse van marketing campagnes en ROI tracking',
        tags: ['Marketing', 'ROI', 'Campagnes']
      }
    ]

    const form = ref({
      name: '',
      email: '',
      message: ''
    })

    const handleScroll = () => {
      isScrolled.value = window.scrollY > 50
    }

    const toggleMobileMenu = () => {
      mobileMenuOpen.value = !mobileMenuOpen.value
    }

    const closeMobileMenu = () => {
      mobileMenuOpen.value = false
    }

    const submitForm = async () => {
      isSubmitting.value = true
      await new Promise(resolve => setTimeout(resolve, 2000))
      form.value = { name: '', email: '', message: '' }
      isSubmitting.value = false
      alert('Bedankt voor uw bericht! We nemen binnen 24 uur contact met u op.')
    }

    onMounted(() => {
      window.addEventListener('scroll', handleScroll)
    })

    onUnmounted(() => {
      window.removeEventListener('scroll', handleScroll)
    })

    return {
      mobileMenuOpen,
      isScrolled,
      isSubmitting,
      services,
      projects,
      form,
      toggleMobileMenu,
      closeMobileMenu,
      submitForm
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

html {
  scroll-behavior: smooth;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  line-height: 1.6;
  color: #ffffff;
  background-color: #000000;
  overflow-x: hidden;
}

#app {
  min-height: 100vh;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

/* Navigation */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  padding: 1rem 0;
  transition: all 0.3s ease;
  backdrop-filter: blur(20px);
}

.navbar.scrolled {
  background-color: rgba(0, 0, 0, 0.8);
  backdrop-filter: blur(20px);
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.logo-icon {
  width: 40px;
  height: 40px;
  background: linear-gradient(135deg, #ffffff, #00d4ff);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  font-weight: 700;
  color: #000;
  box-shadow: 0 8px 32px rgba(0, 212, 255, 0.3);
}

.logo-text {
  font-size: 1.5rem;
  font-weight: 700;
  background: linear-gradient(135deg, #ffffff, #00d4ff);
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
  transition: all 0.3s ease;
  position: relative;
}

.nav-link:hover {
  color: #00d4ff;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: linear-gradient(135deg, #ffffff, #00d4ff);
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
  background-color: rgba(0, 0, 0, 0.95);
  backdrop-filter: blur(20px);
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
  color: #00d4ff;
}

/* Hero Section */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, #000000 0%, #1a1a2e 50%, #16213e 100%);
}

.floating-shapes {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  overflow: hidden;
}

.shape {
  position: absolute;
  border-radius: 50%;
  background: linear-gradient(135deg, rgba(0, 212, 255, 0.1), rgba(255, 255, 255, 0.05));
  animation: float 20s infinite linear;
}

.shape-1 {
  width: 300px;
  height: 300px;
  top: 10%;
  left: 10%;
  animation-delay: 0s;
}

.shape-2 {
  width: 200px;
  height: 200px;
  top: 60%;
  right: 20%;
  animation-delay: -5s;
}

.shape-3 {
  width: 150px;
  height: 150px;
  bottom: 20%;
  left: 20%;
  animation-delay: -10s;
}

.shape-4 {
  width: 100px;
  height: 100px;
  top: 30%;
  right: 60%;
  animation-delay: -15s;
}

@keyframes float {
  0%, 100% { transform: translateY(0px) rotate(0deg); }
  25% { transform: translateY(-20px) rotate(90deg); }
  50% { transform: translateY(0px) rotate(180deg); }
  75% { transform: translateY(20px) rotate(270deg); }
}

.gradient-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: radial-gradient(circle at 30% 20%, rgba(0, 212, 255, 0.1) 0%, transparent 50%);
}

.hero .container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  position: relative;
  z-index: 2;
}

.hero-title {
  font-size: 4rem;
  font-weight: 800;
  line-height: 1.1;
  margin-bottom: 2rem;
}

.title-line {
  display: block;
  background: linear-gradient(135deg, #ffffff, #00d4ff);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.title-accent {
  display: block;
  font-size: 1.5rem;
  color: #00d4ff;
  font-weight: 400;
  margin-top: 1rem;
}

.hero-description {
  font-size: 1.3rem;
  color: #cccccc;
  margin-bottom: 3rem;
  line-height: 1.7;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.btn {
  display: inline-block;
  padding: 1rem 2rem;
  text-decoration: none;
  border-radius: 50px;
  font-weight: 600;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
  font-size: 1rem;
}

.btn-primary {
  background: linear-gradient(135deg, #00d4ff, #0099cc);
  color: #000000;
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 30px rgba(0, 212, 255, 0.4);
}

.btn-secondary {
  background: transparent;
  color: #ffffff;
  border: 2px solid #ffffff;
}

.btn-secondary:hover {
  background: #ffffff;
  color: #000000;
  transform: translateY(-2px);
}

.hero-visual {
  display: flex;
  justify-content: center;
  align-items: center;
}

.data-orb {
  position: relative;
  width: 400px;
  height: 400px;
}

.orb-core {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 120px;
  height: 120px;
  background: radial-gradient(circle, #00d4ff, #0099cc);
  border-radius: 50%;
  box-shadow: 0 0 50px rgba(0, 212, 255, 0.5);
  animation: pulse 3s infinite;
}

.orb-ring {
  position: absolute;
  top: 50%;
  left: 50%;
  border: 2px solid rgba(0, 212, 255, 0.3);
  border-radius: 50%;
  animation: rotate 20s infinite linear;
}

.orb-ring-1 {
  width: 200px;
  height: 200px;
  transform: translate(-50%, -50%);
}

.orb-ring-2 {
  width: 300px;
  height: 300px;
  transform: translate(-50%, -50%);
  animation-direction: reverse;
  animation-duration: 15s;
}

.orb-ring-3 {
  width: 400px;
  height: 400px;
  transform: translate(-50%, -50%);
  animation-duration: 25s;
}

@keyframes rotate {
  from { transform: translate(-50%, -50%) rotate(0deg); }
  to { transform: translate(-50%, -50%) rotate(360deg); }
}

@keyframes pulse {
  0%, 100% { transform: translate(-50%, -50%) scale(1); }
  50% { transform: translate(-50%, -50%) scale(1.1); }
}

.data-points {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.data-point {
  position: absolute;
  width: 8px;
  height: 8px;
  background: #00d4ff;
  border-radius: 50%;
  animation: dataFloat 4s infinite;
}

.data-point:nth-child(1) { top: 10%; left: 20%; animation-delay: 0s; }
.data-point:nth-child(2) { top: 20%; right: 15%; animation-delay: 0.5s; }
.data-point:nth-child(3) { top: 40%; left: 10%; animation-delay: 1s; }
.data-point:nth-child(4) { top: 50%; right: 25%; animation-delay: 1.5s; }
.data-point:nth-child(5) { bottom: 30%; left: 30%; animation-delay: 2s; }
.data-point:nth-child(6) { bottom: 20%; right: 20%; animation-delay: 2.5s; }
.data-point:nth-child(7) { bottom: 40%; left: 50%; animation-delay: 3s; }
.data-point:nth-child(8) { bottom: 10%; right: 40%; animation-delay: 3.5s; }

@keyframes dataFloat {
  0%, 100% { transform: translateY(0px); opacity: 1; }
  50% { transform: translateY(-10px); opacity: 0.7; }
}

.scroll-indicator {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  animation: bounce 2s infinite;
}

.scroll-arrow {
  width: 2px;
  height: 30px;
  background: linear-gradient(to bottom, #ffffff, transparent);
  position: relative;
}

.scroll-arrow::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: -3px;
  width: 8px;
  height: 8px;
  border-right: 2px solid #ffffff;
  border-bottom: 2px solid #ffffff;
  transform: rotate(45deg);
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% { transform: translateX(-50%) translateY(0); }
  40% { transform: translateX(-50%) translateY(-10px); }
  60% { transform: translateX(-50%) translateY(-5px); }
}

/* Sections */
.services, .portfolio, .contact {
  padding: 8rem 0;
  position: relative;
}

.section-header {
  text-align: center;
  margin-bottom: 5rem;
}

.section-title {
  font-size: 3.5rem;
  font-weight: 800;
  margin-bottom: 1rem;
  background: linear-gradient(135deg, #ffffff, #00d4ff);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.section-subtitle {
  font-size: 1.3rem;
  color: #cccccc;
  max-width: 600px;
  margin: 0 auto;
  line-height: 1.6;
}

/* Services */
.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.service-card {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 20px;
  padding: 2.5rem;
  transition: all 0.3s ease;
  backdrop-filter: blur(20px);
}

.service-card:hover {
  transform: translateY(-10px);
  border-color: #00d4ff;
  box-shadow: 0 20px 40px rgba(0, 212, 255, 0.2);
}

.service-icon {
  position: relative;
  margin-bottom: 1.5rem;
}

.icon-bg {
  width: 80px;
  height: 80px;
  background: linear-gradient(135deg, rgba(0, 212, 255, 0.2), rgba(255, 255, 255, 0.1));
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1rem;
}

.icon-emoji {
  font-size: 2.5rem;
}

.service-card h3 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  color: #ffffff;
}

.service-card p {
  color: #cccccc;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.service-features {
  list-style: none;
}

.service-features li {
  color: #ffffff;
  margin-bottom: 0.5rem;
  padding-left: 1.5rem;
  position: relative;
}

.service-features li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #00d4ff;
  font-weight: bold;
}

/* Portfolio */
.portfolio {
  background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 100%);
}

.portfolio-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
}

.portfolio-item {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 20px;
  overflow: hidden;
  transition: all 0.3s ease;
  backdrop-filter: blur(20px);
}

.portfolio-item:hover {
  transform: translateY(-10px);
  border-color: #00d4ff;
  box-shadow: 0 20px 40px rgba(0, 212, 255, 0.2);
}

.portfolio-image {
  height: 200px;
  overflow: hidden;
}

.image-placeholder {
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, #1a1a2e, #16213e);
  display: flex;
  align-items: center;
  justify-content: center;
}

.chart-preview {
  display: flex;
  align-items: end;
  gap: 0.5rem;
  height: 120px;
}

.chart-bar {
  width: 20px;
  background: linear-gradient(135deg, #00d4ff, #0099cc);
  border-radius: 4px;
  animation: chartGrow 1s ease-out;
}

@keyframes chartGrow {
  from { height: 0; }
  to { height: var(--height); }
}

.portfolio-content {
  padding: 2rem;
}

.portfolio-content h3 {
  font-size: 1.3rem;
  margin-bottom: 0.5rem;
  color: #ffffff;
}

.portfolio-content p {
  color: #cccccc;
  line-height: 1.6;
  margin-bottom: 1rem;
}

.portfolio-tags {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
}

.tag {
  background: rgba(0, 212, 255, 0.2);
  color: #00d4ff;
  padding: 0.25rem 0.75rem;
  border-radius: 15px;
  font-size: 0.9rem;
}

/* Contact */
.contact {
  background: linear-gradient(135deg, #000000 0%, #1a1a2e 100%);
}

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: start;
}

.contact-form {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 20px;
  padding: 2.5rem;
  backdrop-filter: blur(20px);
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 1rem;
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 12px;
  color: #ffffff;
  font-size: 1rem;
  transition: all 0.3s ease;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #00d4ff;
  background: rgba(255, 255, 255, 0.1);
}

.form-group input::placeholder,
.form-group textarea::placeholder {
  color: #666;
}

.contact-info {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.contact-method {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1.5rem;
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 16px;
  backdrop-filter: blur(20px);
}

.method-icon {
  font-size: 2rem;
}

.contact-method h3 {
  color: #ffffff;
  font-size: 1.2rem;
  margin-bottom: 0.25rem;
}

.contact-method p {
  color: #cccccc;
}

/* Footer */
.footer {
  background: #000000;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding: 3rem 0;
  text-align: center;
}

.footer-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}

.footer-logo {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.footer-logo .logo-icon {
  width: 32px;
  height: 32px;
  font-size: 1.2rem;
}

.footer-logo .logo-text {
  font-size: 1.2rem;
}

.footer p {
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
  
  .hero .container {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 2rem;
  }
  
  .hero-title {
    font-size: 2.5rem;
  }
  
  .data-orb {
    width: 300px;
    height: 300px;
  }
  
  .orb-ring-1 { width: 150px; height: 150px; }
  .orb-ring-2 { width: 225px; height: 225px; }
  .orb-ring-3 { width: 300px; height: 300px; }
  
  .contact-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .hero-buttons {
    justify-content: center;
  }
  
  .services-grid {
    grid-template-columns: 1fr;
  }
  
  .portfolio-grid {
    grid-template-columns: 1fr;
  }
}
</style>
