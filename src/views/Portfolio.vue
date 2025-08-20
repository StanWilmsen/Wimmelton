<template>
  <div class="portfolio">
    <!-- Header Section -->
    <section class="page-header">
      <div class="container">
        <h1 class="page-title">Portfolio</h1>
        <p class="page-subtitle">
          Bekijk enkele van onze succesvolle projecten en ontdek hoe we data hebben omgezet in waardevolle inzichten
        </p>
      </div>
    </section>

    <!-- Portfolio Grid -->
    <section class="section">
      <div class="container">
        <div class="portfolio-filters">
          <button 
            v-for="category in categories" 
            :key="category.id"
            @click="filterPortfolio(category.id)"
            :class="['filter-btn', { active: activeFilter === category.id }]"
          >
            {{ category.name }}
          </button>
        </div>

        <div class="portfolio-grid">
          <div 
            v-for="project in filteredProjects" 
            :key="project.id"
            class="portfolio-item"
            @click="openProject(project)"
          >
            <div class="portfolio-image">
              <div class="image-placeholder">
                <div class="chart-preview">
                  <div class="chart-bar" style="height: 70%"></div>
                  <div class="chart-bar" style="height: 90%"></div>
                  <div class="chart-bar" style="height: 60%"></div>
                  <div class="chart-bar" style="height: 85%"></div>
                </div>
              </div>
              <div class="portfolio-overlay">
                <span class="view-project">Bekijk project</span>
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

    <!-- Case Study Section -->
    <section class="section" v-if="selectedProject">
      <div class="container">
        <div class="case-study">
          <div class="case-study-header">
            <h2>{{ selectedProject.title }}</h2>
            <button class="close-btn" @click="closeProject">×</button>
          </div>
          <div class="case-study-content">
            <div class="case-study-info">
              <div class="info-item">
                <h4>Klant</h4>
                <p>{{ selectedProject.client }}</p>
              </div>
              <div class="info-item">
                <h4>Project Type</h4>
                <p>{{ selectedProject.type }}</p>
              </div>
              <div class="info-item">
                <h4>Duur</h4>
                <p>{{ selectedProject.duration }}</p>
              </div>
              <div class="info-item">
                <h4>Technologieën</h4>
                <p>{{ selectedProject.technologies.join(', ') }}</p>
              </div>
            </div>
            <div class="case-study-description">
              <h3>Uitdaging</h3>
              <p>{{ selectedProject.challenge }}</p>
              
              <h3>Oplossing</h3>
              <p>{{ selectedProject.solution }}</p>
              
              <h3>Resultaat</h3>
              <p>{{ selectedProject.result }}</p>
            </div>
            <div class="case-study-visual">
              <div class="visual-container">
                <div class="dashboard-preview">
                  <div class="dashboard-header">
                    <div class="dashboard-title">Dashboard Preview</div>
                  </div>
                  <div class="dashboard-content">
                    <div class="metric-card">
                      <div class="metric-value">+25%</div>
                      <div class="metric-label">Efficiëntie</div>
                    </div>
                    <div class="metric-card">
                      <div class="metric-value">-30%</div>
                      <div class="metric-label">Kosten</div>
                    </div>
                    <div class="metric-card">
                      <div class="metric-value">+40%</div>
                      <div class="metric-label">Inzicht</div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Testimonials Section -->
    <section class="section">
      <div class="container">
        <h2 class="section-title">Wat Klanten Zeggen</h2>
        <div class="testimonials-grid">
          <div class="testimonial-card">
            <div class="testimonial-content">
              <p>"Wimmelton heeft onze data compleet getransformeerd. We hebben nu inzichten die we nooit hadden gedacht te kunnen krijgen."</p>
            </div>
            <div class="testimonial-author">
              <div class="author-info">
                <h4>Sarah van der Berg</h4>
                <p>CEO, TechStart BV</p>
              </div>
            </div>
          </div>
          <div class="testimonial-card">
            <div class="testimonial-content">
              <p>"De dashboards die Wimmelton heeft gebouwd zijn intuïtief en geven ons direct de informatie die we nodig hebben."</p>
            </div>
            <div class="testimonial-author">
              <div class="author-info">
                <h4>Mark Jansen</h4>
                <p>Operations Manager, RetailCorp</p>
              </div>
            </div>
          </div>
          <div class="testimonial-card">
            <div class="testimonial-content">
              <p>"Professioneel, snel en resultaatgericht. Wimmelton heeft onze verwachtingen overtroffen."</p>
            </div>
            <div class="testimonial-author">
              <div class="author-info">
                <h4>Lisa de Vries</h4>
                <p>Data Analyst, FinancePro</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="section cta-section">
      <div class="container">
        <div class="cta-content">
          <h2>Klaar voor uw eigen succesverhaal?</h2>
          <p>Laten we samen kijken hoe we uw data kunnen laten werken voor uw bedrijf.</p>
          <router-link to="/contact" class="btn">Start uw project</router-link>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import { ref, computed } from 'vue'

export default {
  name: 'Portfolio',
  setup() {
    const activeFilter = ref('all')
    const selectedProject = ref(null)

    const categories = [
      { id: 'all', name: 'Alle projecten' },
      { id: 'analytics', name: 'Data Analyse' },
      { id: 'visualization', name: 'Visualisaties' },
      { id: 'dashboard', name: 'Dashboards' },
      { id: 'consulting', name: 'Consultancy' }
    ]

    const projects = [
      {
        id: 1,
        title: 'Retail Performance Dashboard',
        description: 'Compleet dashboard voor retail keten met real-time KPI monitoring',
        client: 'RetailCorp',
        type: 'Dashboard & Analytics',
        duration: '6 weken',
        technologies: ['Power BI', 'SQL', 'Python'],
        tags: ['Dashboard', 'Retail', 'KPI'],
        category: 'dashboard',
        challenge: 'RetailCorp had moeite om hun verkoopprestaties in real-time te monitoren en trends te identificeren.',
        solution: 'We hebben een interactief dashboard gebouwd dat alle verkoopdata integreert en automatisch updates.',
        result: '25% verbetering in besluitvorming en 30% reductie in rapportagetijd.'
      },
      {
        id: 2,
        title: 'Financial Data Analysis',
        description: 'Diepgaande analyse van financiële data voor investeringsbeslissingen',
        client: 'FinancePro',
        type: 'Data Analyse',
        duration: '8 weken',
        technologies: ['Python', 'Pandas', 'Tableau'],
        tags: ['Financiën', 'Analyse', 'Investeringen'],
        category: 'analytics',
        challenge: 'FinancePro had grote hoeveelheden financiële data maar kon geen duidelijke patronen identificeren.',
        solution: 'We hebben geavanceerde statistische analyses uitgevoerd en machine learning modellen toegepast.',
        result: '40% verbetering in investeringsbeslissingen en betere risicomanagement.'
      },
      {
        id: 3,
        title: 'Marketing Campaign Analytics',
        description: 'Comprehensive analyse van marketing campagnes en ROI tracking',
        client: 'TechStart BV',
        type: 'Marketing Analytics',
        duration: '4 weken',
        technologies: ['Google Analytics', 'R', 'D3.js'],
        tags: ['Marketing', 'ROI', 'Campagnes'],
        category: 'analytics',
        challenge: 'TechStart kon niet precies meten welke marketing activiteiten het beste presteerden.',
        solution: 'We hebben een geïntegreerd analytics systeem gebouwd dat alle marketing data combineert.',
        result: '35% verhoging in marketing ROI en betere budget allocatie.'
      },
      {
        id: 4,
        title: 'Supply Chain Visualization',
        description: 'Interactieve visualisatie van supply chain processen en bottlenecks',
        client: 'ManufacturingCo',
        type: 'Supply Chain',
        duration: '10 weken',
        technologies: ['D3.js', 'Node.js', 'MongoDB'],
        tags: ['Supply Chain', 'Visualisatie', 'Processen'],
        category: 'visualization',
        challenge: 'ManufacturingCo had complexe supply chain data die moeilijk te begrijpen was voor het management.',
        solution: 'We hebben interactieve visualisaties gebouwd die de supply chain inzichtelijk maken.',
        result: '20% reductie in supply chain kosten en betere resource planning.'
      },
      {
        id: 5,
        title: 'Customer Behavior Analysis',
        description: 'Analyse van klantgedrag en personalisatie strategieën',
        client: 'E-commercePlus',
        type: 'Customer Analytics',
        duration: '7 weken',
        technologies: ['Python', 'Scikit-learn', 'Power BI'],
        tags: ['Klantgedrag', 'Personalisatie', 'E-commerce'],
        category: 'analytics',
        challenge: 'E-commercePlus wilde hun klanten beter begrijpen om personalisatie te verbeteren.',
        solution: 'We hebben customer segmentation analyses uitgevoerd en predictive models gebouwd.',
        result: '45% verbetering in klanttevredenheid en 28% verhoging in conversie.'
      },
      {
        id: 6,
        title: 'Operational Excellence Dashboard',
        description: 'Dashboard voor operationele KPI\'s en proces optimalisatie',
        client: 'OperationsPro',
        type: 'Operations Dashboard',
        duration: '9 weken',
        technologies: ['Power BI', 'Azure', 'SQL Server'],
        tags: ['Operations', 'KPI', 'Optimalisatie'],
        category: 'dashboard',
        challenge: 'OperationsPro had geen centraal overzicht van hun operationele prestaties.',
        solution: 'We hebben een comprehensive dashboard gebouwd dat alle operationele data integreert.',
        result: '30% verbetering in operationele efficiëntie en betere resource planning.'
      }
    ]

    const filteredProjects = computed(() => {
      if (activeFilter.value === 'all') {
        return projects
      }
      return projects.filter(project => project.category === activeFilter.value)
    })

    const filterPortfolio = (categoryId) => {
      activeFilter.value = categoryId
    }

    const openProject = (project) => {
      selectedProject.value = project
      window.scrollTo({ top: 0, behavior: 'smooth' })
    }

    const closeProject = () => {
      selectedProject.value = null
    }

    return {
      categories,
      activeFilter,
      filteredProjects,
      selectedProject,
      filterPortfolio,
      openProject,
      closeProject
    }
  }
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

.portfolio-filters {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-bottom: 3rem;
  flex-wrap: wrap;
}

.filter-btn {
  padding: 0.75rem 1.5rem;
  background: transparent;
  color: #cccccc;
  border: 2px solid #333;
  border-radius: 25px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-weight: 500;
}

.filter-btn:hover,
.filter-btn.active {
  background: #ffffff;
  color: #000000;
  border-color: #ffffff;
}

.portfolio-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
}

.portfolio-item {
  background-color: rgba(255, 255, 255, 0.05);
  border: 1px solid #333;
  border-radius: 16px;
  overflow: hidden;
  transition: all 0.3s ease;
  cursor: pointer;
}

.portfolio-item:hover {
  transform: translateY(-8px);
  border-color: #ffffff;
  box-shadow: 0 15px 40px rgba(255, 255, 255, 0.15);
}

.portfolio-image {
  position: relative;
  height: 200px;
  overflow: hidden;
}

.image-placeholder {
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, #1a1a1a, #333);
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
  background: linear-gradient(135deg, #ffffff, #cccccc);
  border-radius: 2px;
}

.portfolio-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.portfolio-item:hover .portfolio-overlay {
  opacity: 1;
}

.view-project {
  color: #ffffff;
  font-weight: 600;
  font-size: 1.1rem;
}

.portfolio-content {
  padding: 1.5rem;
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
  background-color: rgba(255, 255, 255, 0.1);
  color: #cccccc;
  padding: 0.25rem 0.75rem;
  border-radius: 15px;
  font-size: 0.9rem;
}

.case-study {
  background-color: rgba(255, 255, 255, 0.05);
  border: 1px solid #333;
  border-radius: 16px;
  padding: 2rem;
  margin-bottom: 3rem;
}

.case-study-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 2rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid #333;
}

.case-study-header h2 {
  font-size: 2rem;
  color: #ffffff;
}

.close-btn {
  background: none;
  border: none;
  color: #cccccc;
  font-size: 2rem;
  cursor: pointer;
  padding: 0;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  transition: all 0.3s ease;
}

.close-btn:hover {
  background-color: rgba(255, 255, 255, 0.1);
  color: #ffffff;
}

.case-study-content {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
  gap: 2rem;
}

.case-study-info {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.info-item h4 {
  color: #cccccc;
  font-size: 0.9rem;
  margin-bottom: 0.5rem;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.info-item p {
  color: #ffffff;
  font-weight: 500;
}

.case-study-description h3 {
  color: #ffffff;
  font-size: 1.3rem;
  margin-bottom: 0.5rem;
  margin-top: 1.5rem;
}

.case-study-description h3:first-child {
  margin-top: 0;
}

.case-study-description p {
  color: #cccccc;
  line-height: 1.6;
  margin-bottom: 1rem;
}

.visual-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.dashboard-preview {
  background-color: rgba(255, 255, 255, 0.1);
  border: 1px solid #333;
  border-radius: 12px;
  padding: 1.5rem;
  width: 100%;
}

.dashboard-header {
  margin-bottom: 1rem;
  padding-bottom: 0.5rem;
  border-bottom: 1px solid #333;
}

.dashboard-title {
  color: #ffffff;
  font-weight: 600;
  text-align: center;
}

.dashboard-content {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}

.metric-card {
  text-align: center;
  padding: 1rem;
  background-color: rgba(255, 255, 255, 0.05);
  border-radius: 8px;
}

.metric-value {
  font-size: 1.5rem;
  font-weight: 700;
  color: #ffffff;
  margin-bottom: 0.25rem;
}

.metric-label {
  font-size: 0.9rem;
  color: #cccccc;
}

.testimonials-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.testimonial-card {
  background-color: rgba(255, 255, 255, 0.05);
  border: 1px solid #333;
  border-radius: 16px;
  padding: 2rem;
  transition: all 0.3s ease;
}

.testimonial-card:hover {
  transform: translateY(-5px);
  border-color: #ffffff;
}

.testimonial-content p {
  color: #cccccc;
  font-style: italic;
  line-height: 1.6;
  margin-bottom: 1.5rem;
  font-size: 1.1rem;
}

.testimonial-author h4 {
  color: #ffffff;
  font-size: 1.1rem;
  margin-bottom: 0.25rem;
}

.testimonial-author p {
  color: #cccccc;
  font-size: 0.9rem;
}

/* Responsive Design */
@media (max-width: 768px) {
  .page-title {
    font-size: 2.5rem;
  }
  
  .portfolio-grid {
    grid-template-columns: 1fr;
  }
  
  .case-study-content {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .dashboard-content {
    grid-template-columns: 1fr;
  }
  
  .testimonials-grid {
    grid-template-columns: 1fr;
  }
}
</style>
