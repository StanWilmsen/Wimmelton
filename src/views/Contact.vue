<template>
  <div class="contact">
    <!-- Header Section -->
    <section class="page-header">
      <div class="container">
        <h1 class="page-title">Contact</h1>
        <p class="page-subtitle">
          Klaar om uw data te laten werken? Neem contact op voor een vrijblijvend gesprek
        </p>
      </div>
    </section>

    <!-- Contact Content -->
    <section class="section">
      <div class="container">
        <div class="contact-grid">
          <!-- Contact Form -->
          <div class="contact-form-section">
            <h2>Stuur ons een bericht</h2>
            <p class="form-description">
              Vul het formulier in en we nemen binnen 24 uur contact met u op
            </p>
            
            <form @submit.prevent="submitForm" class="contact-form">
              <div class="form-group">
                <label for="name">Naam *</label>
                <input 
                  type="text" 
                  id="name" 
                  v-model="form.name" 
                  required
                  placeholder="Uw volledige naam"
                >
              </div>
              
              <div class="form-group">
                <label for="email">E-mail *</label>
                <input 
                  type="email" 
                  id="email" 
                  v-model="form.email" 
                  required
                  placeholder="uw.email@bedrijf.nl"
                >
              </div>
              
              <div class="form-group">
                <label for="company">Bedrijf</label>
                <input 
                  type="text" 
                  id="company" 
                  v-model="form.company" 
                  placeholder="Uw bedrijfsnaam"
                >
              </div>
              
              <div class="form-group">
                <label for="phone">Telefoon</label>
                <input 
                  type="tel" 
                  id="phone" 
                  v-model="form.phone" 
                  placeholder="+31 6 12345678"
                >
              </div>
              
              <div class="form-group">
                <label for="service">Gewenste Dienst</label>
                <select id="service" v-model="form.service">
                  <option value="">Selecteer een dienst</option>
                  <option value="data-analysis">Data Analyse & BI</option>
                  <option value="visualization">Data Visualisatie</option>
                  <option value="auditing">Data Auditing & Kwaliteit</option>
                  <option value="implementation">Implementatie & Training</option>
                  <option value="consulting">Consultancy</option>
                  <option value="other">Anders</option>
                </select>
              </div>
              
              <div class="form-group">
                <label for="message">Bericht *</label>
                <textarea 
                  id="message" 
                  v-model="form.message" 
                  required
                  rows="5"
                  placeholder="Vertel ons over uw project en uitdagingen..."
                ></textarea>
              </div>
              
              <div class="form-group">
                <label class="checkbox-label">
                  <input 
                    type="checkbox" 
                    v-model="form.newsletter"
                  >
                  <span class="checkmark"></span>
                  Ik wil graag op de hoogte blijven van data trends en tips
                </label>
              </div>
              
              <button type="submit" class="btn submit-btn" :disabled="isSubmitting">
                <span v-if="isSubmitting">Versturen...</span>
                <span v-else>Verstuur bericht</span>
              </button>
            </form>
          </div>

          <!-- Contact Info -->
          <div class="contact-info-section">
            <h2>Contact Informatie</h2>
            
            <div class="contact-methods">
              <div class="contact-method">
                <div class="method-icon">📧</div>
                <div class="method-content">
                  <h3>E-mail</h3>
                  <p>info@wimmelton.nl</p>
                  <p class="method-note">Reactie binnen 24 uur</p>
                </div>
              </div>
              
              <div class="contact-method">
                <div class="method-icon">📱</div>
                <div class="method-content">
                  <h3>Telefoon</h3>
                  <p>+31 6 12345678</p>
                  <p class="method-note">Ma-Vr 9:00-17:00</p>
                </div>
              </div>
              
              <div class="contact-method">
                <div class="method-icon">💼</div>
                <div class="method-content">
                  <h3>LinkedIn</h3>
                  <p>linkedin.com/company/wimmelton</p>
                  <p class="method-note">Volg ons voor updates</p>
                </div>
              </div>
            </div>

            <div class="consultation-card">
              <h3>Gratis Consultatie</h3>
              <p>
                Boek een gratis 30-minuten gesprek om te bespreken hoe we uw data-uitdagingen kunnen oplossen.
              </p>
              <a href="#" class="btn btn-secondary">Plan consultatie</a>
            </div>

            <div class="office-hours">
              <h3>Kantooruren</h3>
              <div class="hours-grid">
                <div class="day">Maandag - Vrijdag</div>
                <div class="time">9:00 - 17:00</div>
                <div class="day">Zaterdag</div>
                <div class="time">10:00 - 14:00</div>
                <div class="day">Zondag</div>
                <div class="time">Gesloten</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- FAQ Section -->
    <section class="section">
      <div class="container">
        <h2 class="section-title">Veelgestelde Vragen</h2>
        <div class="faq-grid">
          <div class="faq-item" v-for="(faq, index) in faqs" :key="index">
            <div class="faq-question" @click="toggleFaq(index)">
              <h3>{{ faq.question }}</h3>
              <span class="faq-toggle" :class="{ 'open': openFaq === index }">+</span>
            </div>
            <div class="faq-answer" :class="{ 'open': openFaq === index }">
              <p>{{ faq.answer }}</p>
            </div>
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
            <a href="tel:+31612345678" class="btn">Bel ons direct</a>
            <a href="mailto:info@wimmelton.nl" class="btn btn-secondary">Stuur e-mail</a>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'Contact',
  setup() {
    const form = ref({
      name: '',
      email: '',
      company: '',
      phone: '',
      service: '',
      message: '',
      newsletter: false
    })

    const isSubmitting = ref(false)
    const openFaq = ref(null)

    const faqs = [
      {
        question: "Hoe lang duurt een typisch project?",
        answer: "Projecten variëren van 2 weken tot 3 maanden, afhankelijk van de complexiteit. We geven altijd een duidelijke tijdlijn tijdens de eerste consultatie."
      },
      {
        question: "Wat zijn de kosten van uw diensten?",
        answer: "We bieden verschillende pakketten aan, startend vanaf €2.500. De exacte prijs hangt af van uw specifieke behoeften en project scope."
      },
      {
        question: "Werkt u ook met kleine bedrijven?",
        answer: "Absoluut! We werken met bedrijven van alle groottes. Onze oplossingen zijn schaalbaar en passen bij uw budget en behoeften."
      },
      {
        question: "Biedt u ook ondersteuning na het project?",
        answer: "Ja, alle projecten omvatten een periode van ondersteuning. We bieden ook langdurige ondersteuning en training aan."
      },
      {
        question: "Welke technologieën gebruikt u?",
        answer: "We werken met moderne tools zoals Power BI, Tableau, Python, R, SQL en meer. De keuze hangt af van uw bestaande infrastructuur en wensen."
      },
      {
        question: "Kunnen jullie ook bestaande systemen integreren?",
        answer: "Ja, we zijn ervaren in het integreren van bestaande systemen en data bronnen. We maken gebruik van wat u al heeft en vullen aan waar nodig."
      }
    ]

    const submitForm = async () => {
      isSubmitting.value = true
      
      // Simuleer form submission
      await new Promise(resolve => setTimeout(resolve, 2000))
      
      // Reset form
      form.value = {
        name: '',
        email: '',
        company: '',
        phone: '',
        service: '',
        message: '',
        newsletter: false
      }
      
      isSubmitting.value = false
      alert('Bedankt voor uw bericht! We nemen binnen 24 uur contact met u op.')
    }

    const toggleFaq = (index) => {
      openFaq.value = openFaq.value === index ? null : index
    }

    return {
      form,
      isSubmitting,
      faqs,
      openFaq,
      submitForm,
      toggleFaq
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

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  margin-top: 2rem;
}

.contact-form-section h2,
.contact-info-section h2 {
  font-size: 2rem;
  margin-bottom: 1rem;
  color: #ffffff;
}

.form-description {
  color: #cccccc;
  margin-bottom: 2rem;
  line-height: 1.6;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.form-group {
  display: flex;
  flex-direction: column;
}

.form-group label {
  color: #ffffff;
  margin-bottom: 0.5rem;
  font-weight: 500;
}

.form-group input,
.form-group select,
.form-group textarea {
  padding: 0.75rem;
  background-color: rgba(255, 255, 255, 0.05);
  border: 1px solid #333;
  border-radius: 8px;
  color: #ffffff;
  font-size: 1rem;
  transition: all 0.3s ease;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #ffffff;
  background-color: rgba(255, 255, 255, 0.1);
}

.form-group input::placeholder,
.form-group textarea::placeholder {
  color: #666;
}

.checkbox-label {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  cursor: pointer;
  color: #cccccc;
  font-size: 0.9rem;
}

.checkbox-label input[type="checkbox"] {
  width: auto;
  margin: 0;
}

.submit-btn {
  margin-top: 1rem;
  padding: 1rem 2rem;
  font-size: 1.1rem;
}

.submit-btn:disabled {
  opacity: 0.6;
  cursor: not-allowed;
}

.contact-methods {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  margin-bottom: 2rem;
}

.contact-method {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
}

.method-icon {
  font-size: 2rem;
  margin-top: 0.25rem;
}

.method-content h3 {
  color: #ffffff;
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
}

.method-content p {
  color: #cccccc;
  margin-bottom: 0.25rem;
}

.method-note {
  font-size: 0.9rem;
  color: #666;
  font-style: italic;
}

.consultation-card {
  background-color: rgba(255, 255, 255, 0.05);
  border: 1px solid #333;
  border-radius: 16px;
  padding: 2rem;
  margin-bottom: 2rem;
  text-align: center;
}

.consultation-card h3 {
  color: #ffffff;
  font-size: 1.3rem;
  margin-bottom: 1rem;
}

.consultation-card p {
  color: #cccccc;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.office-hours h3 {
  color: #ffffff;
  font-size: 1.3rem;
  margin-bottom: 1rem;
}

.hours-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0.5rem;
}

.hours-grid .day {
  color: #cccccc;
  font-weight: 500;
}

.hours-grid .time {
  color: #666;
  text-align: right;
}

.faq-grid {
  display: grid;
  gap: 1rem;
  margin-top: 3rem;
}

.faq-item {
  background-color: rgba(255, 255, 255, 0.05);
  border: 1px solid #333;
  border-radius: 12px;
  overflow: hidden;
}

.faq-question {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.5rem;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.faq-question:hover {
  background-color: rgba(255, 255, 255, 0.05);
}

.faq-question h3 {
  color: #ffffff;
  font-size: 1.1rem;
  margin: 0;
}

.faq-toggle {
  color: #cccccc;
  font-size: 1.5rem;
  font-weight: 700;
  transition: transform 0.3s ease;
}

.faq-toggle.open {
  transform: rotate(45deg);
}

.faq-answer {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease;
  background-color: rgba(0, 0, 0, 0.2);
}

.faq-answer.open {
  max-height: 200px;
}

.faq-answer p {
  padding: 0 1.5rem 1.5rem;
  color: #cccccc;
  line-height: 1.6;
  margin: 0;
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
  
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .hours-grid {
    grid-template-columns: 1fr;
    text-align: center;
  }
  
  .hours-grid .time {
    text-align: center;
  }
  
  .cta-buttons {
    flex-direction: column;
    align-items: center;
  }
}
</style>
