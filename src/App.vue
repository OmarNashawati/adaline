<script setup>
import FAQSection from './components/sections/FAQSection.vue'
import FeaturesSection from './components/sections/FeaturesSection.vue'
import FooterSection from './components/sections/FooterSection.vue'
import Hero from './components/sections/Hero.vue'
import PricingSection from './components/sections/PricingSection.vue'
import TestimonialsSection from './components/sections/TestimonialsSection.vue'
import WhyUsSection from './components/sections/WhyUsSection.vue'
import Modal from './components/ui/Modal.vue'
import Navbar from './components/ui/navbar.vue'
</script>

<template>
  <Navbar />

  <main>
    <Hero />
    <WhyUsSection />
    <FeaturesSection />
    <TestimonialsSection />
    <PricingSection />
    <FAQSection />
    <FooterSection />
    <Modal />
  </main>
</template>

<style lang="scss" scoped></style>
