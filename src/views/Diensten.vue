<template>
  <div class="diensten">
    <!-- Header Section -->
    <section class="page-header">
      <div class="container">
        <h1 class="page-title">Onze Diensten</h1>
        <p class="page-subtitle">
          Van data-analyse tot implementatie - wij bieden end-to-end oplossingen voor uw data-uitdagingen
        </p>
      </div>
    </section>

    <!-- Services Grid -->
    <section class="section">
      <div class="container">
        <div class="grid grid-2">
          <div class="service-card">
            <div class="service-icon">📊</div>
            <h3>Data Analyse & Business Intelligence</h3>
            <p>
              Diepgaande analyses van uw bedrijfsdata om trends, patronen en kansen te identificeren. 
              We bouwen dashboards en rapporten die u helpen betere beslissingen te nemen.
            </p>
            <ul class="service-features">
              <li>KPI dashboards</li>
              <li>Trend analyses</li>
              <li>Predictive analytics</li>
              <li>Performance monitoring</li>
            </ul>
          </div>

          <div class="service-card">
            <div class="service-icon">🎨</div>
            <h3>Data Visualisatie</h3>
            <p>
              Complexe data omzetten in heldere, overtuigende visualisaties. 
              Van eenvoudige grafieken tot interactieve dashboards die iedereen begrijpt.
            </p>
            <ul class="service-features">
              <li>Interactieve dashboards</li>
              <li>Infographics</li>
              <li>Presentatie slides</li>
              <li>Real-time monitoring</li>
            </ul>
          </div>

          <div class="service-card">
            <div class="service-icon">🔍</div>
            <h3>Data Auditing & Kwaliteit</h3>
            <p>
              Beoordeling van uw data-infrastructuur en -kwaliteit. 
              We identificeren problemen en stellen verbeteringen voor.
            </p>
            <ul class="service-features">
              <li>Data kwaliteitscontrole</li>
              <li>Infrastructuur audit</li>
              <li>Compliance check</li>
              <li>Verbeteringsplan</li>
            </ul>
          </div>

          <div class="service-card">
            <div class="service-icon">🚀</div>
            <h3>Implementatie & Training</h3>
            <p>
              Niet alleen analyseren, maar ook implementeren. 
              We helpen u bij het implementeren van data-gedreven processen en trainen uw team.
            </p>
            <ul class="service-features">
              <li>Proces implementatie</li>
              <li>Team training</li>
              <li>Change management</li>
              <li>Ondersteuning</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- Process Section -->
    <section class="section">
      <div class="container">
        <h2 class="section-title">Hoe We Werken</h2>
        <div class="workflow">
          <div class="workflow-step">
            <div class="step-icon">💬</div>
            <h3>1. Consultatie</h3>
            <p>We bespreken uw uitdagingen en doelen om de beste aanpak te bepalen.</p>
          </div>
          <div class="workflow-arrow">→</div>
          <div class="workflow-step">
            <div class="step-icon">📋</div>
            <h3>2. Plan</h3>
            <p>We maken een gedetailleerd plan met tijdlijn en deliverables.</p>
          </div>
          <div class="workflow-arrow">→</div>
          <div class="workflow-step">
            <div class="step-icon">⚙️</div>
            <h3>3. Uitvoering</h3>
            <p>We voeren het plan uit met regelmatige updates en feedback.</p>
          </div>
          <div class="workflow-arrow">→</div>
          <div class="workflow-step">
            <div class="step-icon">✅</div>
            <h3>4. Resultaat</h3>
            <p>We leveren het eindresultaat en zorgen voor een soepele overgang.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Pricing Section -->
    <section class="section">
      <div class="container">
        <h2 class="section-title">Prijzen & Pakketten</h2>
        <p class="section-subtitle">
          Flexibele oplossingen die passen bij uw behoeften en budget
        </p>
        <div class="pricing-grid">
          <div class="pricing-card">
            <h3>Starter</h3>
            <div class="price">€2.500</div>
            <p class="price-description">Basis data-analyse en visualisatie</p>
            <ul class="pricing-features">
              <li>Data audit & rapportage</li>
              <li>Basis dashboard</li>
              <li>5 KPI visualisaties</li>
              <li>1 maand ondersteuning</li>
            </ul>
            <router-link to="/contact" class="btn btn-secondary">Neem contact op</router-link>
          </div>

          <div class="pricing-card featured">
            <div class="featured-badge">Populair</div>
            <h3>Professional</h3>
            <div class="price">€5.000</div>
            <p class="price-description">Uitgebreide analyse en implementatie</p>
            <ul class="pricing-features">
              <li>Diepgaande data-analyse</li>
              <li>Interactief dashboard</li>
              <li>10+ KPI visualisaties</li>
              <li>Implementatie ondersteuning</li>
              <li>3 maanden ondersteuning</li>
            </ul>
            <router-link to="/contact" class="btn">Neem contact op</router-link>
          </div>

          <div class="pricing-card">
            <h3>Enterprise</h3>
            <div class="price">Op maat</div>
            <p class="price-description">Volledige data-transformatie</p>
            <ul class="pricing-features">
              <li>End-to-end oplossing</li>
              <li>Custom dashboards</li>
              <li>Team training</li>
              <li>Ongelimiteerde ondersteuning</li>
              <li>Dedicated consultant</li>
            </ul>
            <router-link to="/contact" class="btn btn-secondary">Neem contact op</router-link>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="section cta-section">
      <div class="container">
        <div class="cta-content">
          <h2>Klaar om te beginnen?</h2>
          <p>Laten we samen kijken hoe we uw data kunnen laten werken voor uw bedrijf.</p>
          <div class="cta-buttons">
            <router-link to="/contact" class="btn">Gratis consultatie</router-link>
            <router-link to="/portfolio" class="btn btn-secondary">Bekijk portfolio</router-link>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Diensten'
}
</script>

<style scoped>
.page-header {
  padding: 8rem 0 5rem;
  background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
  text-align: center;
}

.page-title {
  font-size: 3.5rem;
  font-weight: 800;
  margin-bottom: 1rem;
  background: linear-gradient(135deg, #ffffff, #cccccc);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.page-subtitle {
  font-size: 1.3rem;
  color: #cccccc;
  max-width: 700px;
  margin: 0 auto;
  line-height: 1.6;
}

.service-card {
  background-color: rgba(255, 255, 255, 0.05);
  border: 1px solid #333;
  border-radius: 16px;
  padding: 2.5rem;
  transition: all 0.3s ease;
  height: 100%;
}

.service-card:hover {
  transform: translateY(-8px);
  border-color: #ffffff;
  box-shadow: 0 15px 40px rgba(255, 255, 255, 0.15);
}

.service-icon {
  font-size: 3.5rem;
  margin-bottom: 1.5rem;
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
  padding: 0;
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
  color: #cccccc;
  font-weight: bold;
}

.workflow {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  gap: 2rem;
  margin-top: 3rem;
}

.workflow-step {
  text-align: center;
  flex: 1;
  min-width: 200px;
}

.step-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.workflow-step h3 {
  font-size: 1.3rem;
  margin-bottom: 1rem;
  color: #ffffff;
}

.workflow-step p {
  color: #cccccc;
  line-height: 1.6;
}

.workflow-arrow {
  font-size: 2rem;
  color: #cccccc;
  font-weight: bold;
}

.pricing-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.pricing-card {
  background-color: rgba(255, 255, 255, 0.05);
  border: 1px solid #333;
  border-radius: 16px;
  padding: 2.5rem;
  text-align: center;
  position: relative;
  transition: all 0.3s ease;
}

.pricing-card:hover {
  transform: translateY(-5px);
  border-color: #ffffff;
}

.pricing-card.featured {
  border-color: #ffffff;
  box-shadow: 0 10px 30px rgba(255, 255, 255, 0.2);
}

.featured-badge {
  position: absolute;
  top: -15px;
  left: 50%;
  transform: translateX(-50%);
  background: linear-gradient(135deg, #ffffff, #cccccc);
  color: #000000;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.9rem;
  font-weight: 600;
}

.pricing-card h3 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  color: #ffffff;
}

.price {
  font-size: 2.5rem;
  font-weight: 800;
  margin-bottom: 0.5rem;
  background: linear-gradient(135deg, #ffffff, #cccccc);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.price-description {
  color: #cccccc;
  margin-bottom: 2rem;
}

.pricing-features {
  list-style: none;
  padding: 0;
  margin-bottom: 2rem;
}

.pricing-features li {
  color: #ffffff;
  margin-bottom: 0.8rem;
  padding-left: 1.5rem;
  position: relative;
}

.pricing-features li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #cccccc;
  font-weight: bold;
}

.cta-buttons {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
}

/* Responsive Design */
@media (max-width: 768px) {
  .page-title {
    font-size: 2.5rem;
  }
  
  .workflow {
    flex-direction: column;
    text-align: center;
  }
  
  .workflow-arrow {
    transform: rotate(90deg);
  }
  
  .pricing-grid {
    grid-template-columns: 1fr;
  }
  
  .cta-buttons {
    flex-direction: column;
    align-items: center;
  }
}
</style>
