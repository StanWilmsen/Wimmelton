<template>
  <div class="home">
    <!-- Hero Section -->
    <section class="hero">
      <div class="container">
        <div class="hero-content">
          <h1 class="hero-title">
            Data Analyses & Visualisaties
            <span class="hero-subtitle">die resultaten leveren</span>
          </h1>
          <p class="hero-description">
            Wimmelton helpt bedrijven om hun data te begrijpen en te benutten. 
            Van complexe analyses tot heldere visualisaties - wij maken data toegankelijk en actiegericht.
          </p>
          <div class="hero-buttons">
            <router-link to="/diensten" class="btn">Ontdek onze diensten</router-link>
            <router-link to="/contact" class="btn btn-secondary">Neem contact op</router-link>
          </div>
        </div>
        <div class="hero-visual">
          <div class="data-visualization">
            <div class="chart-container">
              <div class="chart-bar" style="height: 60%"></div>
              <div class="chart-bar" style="height: 80%"></div>
              <div class="chart-bar" style="height: 45%"></div>
              <div class="chart-bar" style="height: 95%"></div>
              <div class="chart-bar" style="height: 70%"></div>
            </div>
            <div class="data-points">
              <div class="data-point"></div>
              <div class="data-point"></div>
              <div class="data-point"></div>
              <div class="data-point"></div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Features Section -->
    <section class="section">
      <div class="container">
        <h2 class="section-title">Waarom Wimmelton?</h2>
        <p class="section-subtitle">
          Wij combineren technische expertise met zakelijk inzicht om uw data te laten werken
        </p>
        <div class="grid grid-3">
          <div class="card">
            <div class="card-icon">📊</div>
            <h3>Data Analyse</h3>
            <p>Diepgaande analyses die patronen onthullen en kansen identificeren in uw data.</p>
          </div>
          <div class="card">
            <div class="card-icon">🎨</div>
            <h3>Visualisaties</h3>
            <p>Helder en overtuigend gepresenteerde data die iedereen begrijpt en kan gebruiken.</p>
          </div>
          <div class="card">
            <div class="card-icon">🚀</div>
            <h3>Resultaten</h3>
            <p>Concrete acties en strategieën gebaseerd op data-gedreven inzichten.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Process Section -->
    <section class="section">
      <div class="container">
        <h2 class="section-title">Onze Aanpak</h2>
        <p class="section-subtitle">
          Een gestructureerde methode om uw data te transformeren in waardevolle inzichten
        </p>
        <div class="process-steps">
          <div class="process-step">
            <div class="step-number">1</div>
            <h3>Data Verzameling</h3>
            <p>We verzamelen en structureren alle relevante data uit uw systemen.</p>
          </div>
          <div class="process-step">
            <div class="step-number">2</div>
            <h3>Analyse & Patronen</h3>
            <p>Diepgaande analyse om trends, patronen en afwijkingen te identificeren.</p>
          </div>
          <div class="process-step">
            <div class="step-number">3</div>
            <h3>Visualisatie</h3>
            <p>Helder gepresenteerde resultaten in dashboards en rapporten.</p>
          </div>
          <div class="process-step">
            <div class="step-number">4</div>
            <h3>Actie & Implementatie</h3>
            <p>Concrete aanbevelingen en ondersteuning bij implementatie.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="section cta-section">
      <div class="container">
        <div class="cta-content">
          <h2>Klaar om uw data te laten werken?</h2>
          <p>Laten we samen kijken hoe we uw data kunnen omzetten in meetbare resultaten.</p>
          <router-link to="/contact" class="btn">Gratis consultatie</router-link>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Home'
}
</script>

<style scoped>
.hero {
  padding: 8rem 0 5rem;
  background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
  position: relative;
  overflow: hidden;
}

.hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: radial-gradient(circle at 30% 20%, rgba(255, 255, 255, 0.03) 0%, transparent 50%);
}

.hero .container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 800;
  line-height: 1.1;
  margin-bottom: 1.5rem;
  background: linear-gradient(135deg, #ffffff, #cccccc);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-subtitle {
  display: block;
  font-size: 2rem;
  color: #cccccc;
  font-weight: 400;
}

.hero-description {
  font-size: 1.2rem;
  color: #cccccc;
  margin-bottom: 2rem;
  line-height: 1.7;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.hero-visual {
  display: flex;
  justify-content: center;
  align-items: center;
}

.data-visualization {
  position: relative;
  width: 300px;
  height: 300px;
}

.chart-container {
  display: flex;
  align-items: end;
  gap: 1rem;
  height: 200px;
  margin-bottom: 2rem;
}

.chart-bar {
  width: 40px;
  background: linear-gradient(135deg, #ffffff, #cccccc);
  border-radius: 4px;
  transition: all 0.3s ease;
  animation: chartAnimation 2s ease-out;
}

.chart-bar:nth-child(1) { animation-delay: 0.1s; }
.chart-bar:nth-child(2) { animation-delay: 0.2s; }
.chart-bar:nth-child(3) { animation-delay: 0.3s; }
.chart-bar:nth-child(4) { animation-delay: 0.4s; }
.chart-bar:nth-child(5) { animation-delay: 0.5s; }

@keyframes chartAnimation {
  from { height: 0; }
  to { height: var(--height); }
}

.data-points {
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.data-point {
  width: 12px;
  height: 12px;
  background: #ffffff;
  border-radius: 50%;
  animation: pulse 2s infinite;
}

.data-point:nth-child(2) { animation-delay: 0.5s; }
.data-point:nth-child(3) { animation-delay: 1s; }
.data-point:nth-child(4) { animation-delay: 1.5s; }

@keyframes pulse {
  0%, 100% { transform: scale(1); opacity: 1; }
  50% { transform: scale(1.2); opacity: 0.7; }
}

.card-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.process-steps {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.process-step {
  text-align: center;
  position: relative;
}

.step-number {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, #ffffff, #cccccc);
  color: #000000;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  font-weight: 700;
  margin: 0 auto 1.5rem;
}

.process-step h3 {
  font-size: 1.3rem;
  margin-bottom: 1rem;
  color: #ffffff;
}

.process-step p {
  color: #cccccc;
  line-height: 1.6;
}

.cta-section {
  background: linear-gradient(135deg, #000000, #1a1a1a);
  border-top: 1px solid #333;
  border-bottom: 1px solid #333;
}

.cta-content {
  text-align: center;
}

.cta-content h2 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
  background: linear-gradient(135deg, #ffffff, #cccccc);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.cta-content p {
  font-size: 1.2rem;
  color: #cccccc;
  margin-bottom: 2rem;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

/* Responsive Design */
@media (max-width: 768px) {
  .hero .container {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 2rem;
  }
  
  .hero-title {
    font-size: 2.5rem;
  }
  
  .hero-subtitle {
    font-size: 1.5rem;
  }
  
  .hero-buttons {
    justify-content: center;
  }
  
  .data-visualization {
    width: 250px;
    height: 250px;
  }
  
  .chart-container {
    height: 150px;
  }
  
  .chart-bar {
    width: 30px;
  }
}
</style>
