<template>
  <div class="header-container">
      <header>
      <div class="logo"><img src="../assets/icons/logo.svg" alt="Picto JP"></div>
      <div class="menu">
          <ul>
            <li><a href="#">A propos</a></li>
            <li><a href="#">Compétences</a></li>
            <li><a href="#">Projets</a></li>
          </ul>
        </div>
        <div class="contact">
          <a href="https://www.linkedin.com/in/%F0%9F%9A%80-julien-petit-182580266/" target="_blank"><LinkedinIcon class="icon-size" /></a>
          <a href="https://github.com/Scofrard" target="_blank"><GithubIcon class="icon-size" /></a>
          <a href="https://github.com/Scofrard" target="_blank">CV</a>
        </div>
      <button class="hamburger" @click="isMenuOpen = !isMenuOpen">
        <HamburgerIcon/>
      </button>
      <div v-if="isMenuOpen" class="overlay" @click="isMenuOpen = false"></div>
      <nav :class="{ open: isMenuOpen }">
        <button class="close" @click="isMenuOpen = false"><CloseIcon/></button>
        <div class="menu">
          <ul>
            <li><a href="#">A propos</a></li>
            <li><a href="#">Compétences</a></li>
            <li><a href="#">Projets</a></li>
          </ul>
        </div>
        <div class="contact">
          <a href="https://www.linkedin.com/in/%F0%9F%9A%80-julien-petit-182580266/" target="_blank"><LinkedinIcon class="icon-size" /></a>
          <a href="https://github.com/Scofrard" target="_blank"><GithubIcon class="icon-size" /></a>
          <a href="https://github.com/Scofrard" target="_blank">CV</a>
        </div>
      </nav>
    </header>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import LinkedinIcon from '@/assets/icons/linkedin.svg'
import GithubIcon from '@/assets/icons/github.svg'
import HamburgerIcon from '@/assets/icons/hamburger.svg'
import CloseIcon from '@/assets/icons/close.svg'
import HtmlIcon from '@/assets/icons/html5.svg'

const isMenuOpen = ref(false)
</script>


<style lang="scss">
@use '../styles/header.scss';
</style>