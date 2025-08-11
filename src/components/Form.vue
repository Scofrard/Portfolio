<template>
  <div class="form-container">
    <div>
      <h2>Formulaire</h2>
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss">
@use "@/styles/global.scss" as *;

.form-container {
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
  }
}
</style>
