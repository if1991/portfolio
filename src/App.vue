<template>
  <main class="page" id="top">
    <NavigationBar />
    <HeroSection />
    <AboutSection />
    <SkillsSection />
    <ProjectSection />
    <ContactSection />
  </main>

  <Footer />
</template>

<script setup lang="ts">
import NavigationBar from './components/NavigationBar.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import SkillsSection from './components/SkillsSection.vue'
import ProjectSection from './components/ProjectSection.vue'
import ContactSection from './components/ContactSection.vue'
import Footer from './components/Footer.vue'
</script>
