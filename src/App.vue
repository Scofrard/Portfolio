<template>
  <Header />
  <About />
  <Projects />
  <Skills />
  <Stacks />
  <Form />
  <Footer />
</template>

<script setup>
import Header from './components/Header.vue'
import About from './components/About.vue'
import Projects from './components/Projects.vue'
import Skills from './components/Skills.vue'
import Stacks from './components/Stacks.vue'
import Form from './components/Form.vue'
import Footer from './components/Footer.vue'
</script>

<style lang="scss">
@use './styles/main.scss';
</style>