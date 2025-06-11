<template>
  <header>
    <div class="logo"><img src="./assets/icons/logo.svg" alt="Picto JP"></div>
    <div class="menu">
      <ul>
        <li>A propos</li>
        <li>Compétences</li>
        <li>Projets</li>
     </ul>
    </div>
  <div class="contact">
    <LinkedinIcon />
    <img src="./assets/icons/github.svg" alt="GitHub Icon" />
    <CvIcon />
  </div>
  </header>
</template>

<script setup>
import LinkedinIcon from '@/assets/icons/linkedin.svg'
import CvIcon from '@/assets/icons/cv.svg'
import GithubIcon from '@/assets/icons/github.svg'
import HtmlIcon from '@/assets/icons/html5.svg'
</script>


<style>
</style>