<template>
  <div class="about-container" id="about">
    <div>
      <p id="about-text">
        <span>Passionné par le développement web et le </span>
        <span>design, je suis un créatif curieux et impliqué. </span>
        <span>Spécialisé dans le digital, mon approche </span>
        <span>allie une réflexion centrée sur l'utilisateur </span>
        <span>à la création d'univers graphiques inédits.</span>
      </p>

      <div class="button-group">
        <a
          href="https://www.linkedin.com/in/%F0%9F%9A%80-julien-petit-182580266/"
          target="_blank"
          class="primary-btn"
          aria-label="M'ajouter sur Linkedin"
          >Se connecter sur Linkedin<span class="arrow-right">
            <ConnectIcon /> </span
        ></a>
        <a
          href="/src/assets/pdf/cvjulienpetit.pdf"
          download="cv_julien_petit.pdf"
          target="_blank"
          class="primary-btn"
          aria-label="Télécharger mon CV"
          >Télécharger mon CV<span class="arrow-right">
            <DownloadCvIcon /> </span
        ></a>
      </div>
    </div>
  </div>
</template>

<script setup>
import ConnectIcon from "@/assets/icons/connectlinkedin.svg";
import DownloadCvIcon from "@/assets/icons/downloadcv.svg";

import { onMounted, onBeforeUnmount } from "vue";
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

onMounted(() => {
  const aboutText = document.querySelector("#about-text");
  if (!aboutText) return;

  const lines = aboutText.querySelectorAll("span");

  const tl = gsap.timeline({
    scrollTrigger: {
      trigger: aboutText,
      start: "top 80%",
      end: "bottom 40%",
      scrub: true,
    },
  });

  let delay = 0;
  const stagger = 0.1;
  const duration = 0.4;

  lines.forEach((line) => {
    const text = line.textContent || "";
    line.innerHTML = "";

    const words = text.split(" ");
    const wordSpans = words.map((word, index) => {
      const span = document.createElement("span");
      span.className = "word";
      span.textContent = word + (index < words.length - 1 ? " " : "");
      line.appendChild(span);
      return span;
    });

    if (wordSpans.length === 0) return;

    gsap.set(wordSpans, {
      opacity: 0.1,
    });

    tl.to(
      wordSpans,
      {
        opacity: 1,
        ease: "power2.out",
        duration,
        stagger,
      },
      delay
    );

    delay += wordSpans.length * stagger;
  });
});

onBeforeUnmount(() => {
  ScrollTrigger.getAll().forEach((trigger) => trigger.kill());
});
</script>

<style lang="scss">
@use "@/styles/global.scss" as *;

.about-container {
  background-color: $color-primary;
  overflow-x: hidden;

  div {
    padding: 6rem 2rem;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;

    p {
      color: $color-secondary;
      font-size: 1.5rem;
      margin-bottom: 2rem;
      max-width: 730px;
      width: 100%;

      #about-text {
        display: block;
        line-height: 1.6;
        font-size: 1.5rem;
        white-space: pre-wrap;
        overflow-wrap: break-word;
      }
    }

    .button-group {
      padding: 0;
      display: flex;
      flex-direction: column;

      a {
        svg {
          width: 20px;
          height: 20px;
        }
      }
    }
  }
}

@media (min-width: 1280px) {
  .about-container div {
    max-width: 920px;
    margin: 0 auto;
    padding: 10rem 0rem;

    p {
      font-size: 2.5rem;
      font-weight: 700;
    }

    .button-group {
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: row;
      align-items: flex-start;
      justify-content: flex-start;
      gap: 2rem;
    }
  }
}
</style>
