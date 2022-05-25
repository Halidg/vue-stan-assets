<template>
  <Header />
  <MainSection />
  <TechnologiesSection />
  <ServicesSection /> 
  <PartnershipSection />
  <AchievementsSection />
  <PartnersSection /> 
  <ContactSection />
  <FooterSection />    
</template>

<script>
import Header from './components/Header.vue'
import MainSection from './components/Sections/MainSection.vue'
import TechnologiesSection from './components/Sections/TechnologiesSection.vue'
import ServicesSection from './components/Sections/ServicesSection.vue'
import PartnershipSection from './components/Sections/PatrnershipSection.vue'
import AchievementsSection from './components/Sections/AchievementsSection.vue'
import PartnersSection from './components/Sections/PartnersSection.vue'
import ContactSection from './components/Sections/ContactSection.vue'
import FooterSection from './components/Sections/FooterSection.vue'


export default {
  components: {
    Header,
    MainSection,
    TechnologiesSection,
    ServicesSection,
    PartnershipSection,
    AchievementsSection,
    PartnersSection,
    ContactSection,
    FooterSection
}  
}
</script>

<style lang="scss">

</style>
