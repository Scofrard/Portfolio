<template>
  <Header />
  <About />
  <Projects />
  <Footer />
</template>

<script setup>
import Header from './components/Header.vue'
import About from './components/About.vue'
import Projects from './components/Projects.vue'
import Footer from './components/Footer.vue'
</script>

<style lang="scss">
@use './styles/main.scss';
</style>