<template>
  <div class="projects-container">
    <div>
      <h2>Mes projets</h2>
      <p>Un peu de patience... Encore un peu de figma et de code avant de voir mes plus beaux projets</p>
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss">
@use "@/styles/global.scss" as *;

.projects-container {
  background-color: $color-primary;

  div {
    max-width: 100%;
    width: 1200px;
    margin: 0 auto;

    h2 {
      text-align: center;
      font-family: $font-secondary;
      font-size: 5rem;
      padding: 10rem 0;
    }

    p {
      text-align: center;
      font-family: $font-primary;
      font-size: 1.2rem;
      padding-bottom: 10rem;
      color: $color-secondary;
      font-style: italic;
    }
  }
}
</style>
