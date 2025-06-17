<template>
    <div class="about-container" id="about">
        <div>
            <p id="about-text">
                <span>Passionné par le développement web et le</span><br>
                <span>design, je suis un créatif curieux et impliqué.</span><br>
                <span>Spécialisé dans le digital, mon approche</span><br>
                <span>allie une réflexion centrée sur l’utilisateur</span><br>
                <span>à la création d’univers graphiques inédits.</span>
            </p>
            <div class="button-group">
                <a href="https://www.linkedin.com/in/%F0%9F%9A%80-julien-petit-182580266/" target="_blank"
                    class="primary-btn" aria-label="M'ajouter sur Linkedin">Se connecter sur Linkedin<span class="arrow-right">
                        <ConnectIcon />
                    </span></a>
                <a href="#" target="_blank" class="primary-btn" aria-label="Télécharger mon CV">Télécharger mon CV<span class="arrow-right">
                        <DownloadCvIcon />
                    </span></a>
            </div>
        </div>
    </div>
</template>

<script setup>
import ConnectIcon from '@/assets/icons/connectlinkedin.svg'
import DownloadCvIcon from '@/assets/icons/downloadcv.svg'

import { onMounted, onBeforeUnmount } from 'vue'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
  const lines = gsap.utils.toArray('#about-text span')

  lines.forEach((line) => {
    gsap.from(line, {
      x: -50, 
      opacity: 0,
      duration: 3,
      ease: 'power2.out',
      scrollTrigger: {
        trigger: line,
        start: 'top 80%', 
      },
    })
  })
})

onBeforeUnmount(() => {
  ScrollTrigger.killAll()
})
</script>

<style lang="scss">
@use '@/styles/global.scss' as *;

.about-container {
    background-color: $color-primary;

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

            #about-text span {
              display: block;
              overflow: hidden; // optionnel si tu veux du clip
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