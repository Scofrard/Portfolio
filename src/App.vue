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
    <LinkedinIcon class="icon-size" />
    <GithubIcon class="icon-size" />
    <a href="#">CV</a>
  </div>
  </header>
</template>

<style scoped>
.icon-size {
  width: 60px;
  height: 60px;
}
</style>

<script setup>
import LinkedinIcon from '@/assets/icons/linkedin.svg'
import GithubIcon from '@/assets/icons/github.svg'
import HtmlIcon from '@/assets/icons/html5.svg'
</script>


<style>
.icon-size {
  width: 80px;
  height: 80px;
}
</style>