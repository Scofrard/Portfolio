<template>
  <div class="header-container">
      <header>
      <div class="logo"><img src="../assets/icons/logo.svg" alt="Picto JP"></div>
      <div class="menu">
        <ul>
          <li>A propos</li>
          <li>Compétences</li>
          <li>Projets</li>
        </ul>
      </div>
      <div class="contact">
        <a href="https://www.linkedin.com/in/%F0%9F%9A%80-julien-petit-182580266/" target="_blank"><LinkedinIcon class="icon-size" /></a>
        <a href="https://github.com/Scofrard" target="_blank"><GithubIcon class="icon-size" /></a>
        <a href="https://github.com/Scofrard" target="_blank">CV</a>
      </div>
    </header>
  </div>
</template>

<script setup>
import LinkedinIcon from '@/assets/icons/linkedin.svg'
import GithubIcon from '@/assets/icons/github.svg'
import HtmlIcon from '@/assets/icons/html5.svg'
</script>


<style lang="scss">
@use '../styles/header.scss';
</style>