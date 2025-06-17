<template>
  <div class="header-container">

    <header>
      <Logo class="logo" />
      <div class="menu">
        <ul>
          <li><a href="#about" @click.prevent="scrollTo('#about')">A propos</a></li>
          <li><a href=" #">Compétences</a></li>
          <li><a href="#">Projets</a></li>
        </ul>
      </div>
      <div class="contact">
        <a href="https://github.com/Scofrard" target="_blank" aria-label="Télécharger mon CV">CV</a>
        <a href="https://www.linkedin.com/in/%F0%9F%9A%80-julien-petit-182580266/" target="_blank" aria-label="M'ajouter sur Linkedin">
          <LinkedinIcon class="icon-size" />
        </a>
        <a href="https://github.com/Scofrard" target="_blank" aria-label="Découvrir mon github">
          <GithubIcon class="icon-size" />
        </a>
      </div>
      <button class="hamburger" title="Menu hamburger" @click="isMenuOpen = !isMenuOpen">
        <HamburgerIcon />
      </button>
      <div v-if="isMenuOpen" class="overlay" @click="isMenuOpen = false"></div>
      <nav :class="{ open: isMenuOpen }">
        <button class="close" @click="isMenuOpen = false">
          <CloseIcon />
        </button>
        <div class="menu">
          <ul>
            <li><a href="#">A propos</a></li>
            <li><a href="#">Compétences</a></li>
            <li><a href="#">Projets</a></li>
          </ul>
        </div>
        <div class="contact">
          <a href="https://www.linkedin.com/in/%F0%9F%9A%80-julien-petit-182580266/" target="_blank" aria-label="M'ajouter sur Linkedin">
            <LinkedinDarkIcon class="icon-size" />
          </a>
          <a href="https://github.com/Scofrard" target="_blank" aria-label="Découvrir mon github">
            <GithubDarkIcon class="icon-size" />
          </a>
          <a href="https://github.com/Scofrard" target="_blank" aria-label="Télécharger mon CV">CV</a>
        </div>
      </nav>
    </header>

    <!-- Hero banner -->

    <div class="herobanner">
      <h1>Julien Petit</h1>
      <h2>Le dev qu'il vous faut</h2>
      <p>Designer UI/UX et Développeur front-end freelance en Belgique</p>
      <a href="#" class="primary-btn" aria-label="Me contacter">Me contacter
        <ArrowRightIcon />
      </a>
      <div class="scroll-wrapper">
        <ArrowDropLeftIcon class="scroll-icon" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Logo from '@/assets/icons/logo.svg'
import LinkedinIcon from '@/assets/icons/linkedin.svg'
import LinkedinDarkIcon from '@/assets/icons/linkedindark.svg'
import GithubIcon from '@/assets/icons/github.svg'
import GithubDarkIcon from '@/assets/icons/githubdark.svg'
import HamburgerIcon from '@/assets/icons/hamburger.svg'
import CloseIcon from '@/assets/icons/close.svg'
import ArrowRightIcon from '@/assets/icons/arrowright.svg'
import ArrowDropLeftIcon from '@/assets/icons/arrowdropleft.svg'
import HtmlIcon from '@/assets/icons/html5.svg'

const isMenuOpen = ref(false)


import gsap from 'gsap'
import { ScrollToPlugin } from 'gsap/ScrollToPlugin'

gsap.registerPlugin(ScrollToPlugin)

function scrollTo(target) {
  gsap.to(window, {
    duration: 1.2,
    scrollTo: {
      y: target,
      offsetY: 0,
    },
    ease: 'circ.out'
  })
}
</script>


<style lang="scss">
@use '@/styles/global.scss' as *;

.header-container {
  max-width: 100%;
  height: calc(100vh - 1rem);
  padding-top: 1rem;
  margin: 0 auto;
  background: $color-primary;
  /* HEADER + NAVBAR */
  /* HEADER + NAVBAR */
  /* HEADER + NAVBAR */

  header {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;

    .logo {
      width: 80px;
      height: auto;
    }

    .menu {
      margin-left: 66px;

      ul {
        display: flex;

        li {
          padding: 0 1rem;

          a {
            position: relative;
            color: $color-secondary;
            text-decoration: none;

            &::after {
              content: "";
              position: absolute;
              bottom: -5px;
              left: 0;
              width: 0%;
              height: 2px;
              background-color: $color-secondary;
              transition: width 0.2s ease-in-out;
            }

            &:hover::after {
              width: 100%;
            }
          }
        }
      }
    }

    .contact {
      display: flex;
      align-items: center;
      gap: .5rem;

      a {
        text-decoration: none;
        padding: .5rem;
        color: $color-secondary;

        .icon-size {
          width: 25px;
          height: 25px;
        }
      }
    }

    .hamburger {
      display: none;
      background: none;
      border: none;
      font-size: 3rem;
      cursor: pointer;
    }

    .overlay {
      display: none;
    }

    nav {
      display: none;
    }
  }
}

/* TABLET SCREEN */
/* TABLET SCREEN */
/* TABLET SCREEN */

@media (max-width: 1260px) {
  .header-container {
    header {
      max-width: 1200px;
      padding: 0 2rem;

      .logo {
        width: 70px;
        height: auto;
      }

      .menu {
        margin-left: 76px;
      }
    }
  }
}

/* MOBILE SCREEN */
/* MOBILE SCREEN */
/* MOBILE SCREEN */

@media (max-width: 768px) {
  .header-container {
    header {
      max-width: 100%;
      padding: 0 2rem;

      .logo {
        width: 60px;
        height: auto;
      }

      .menu {
        display: none;
      }

      .contact {
        display: none;
      }

      .hamburger {
        display: block;
        padding: 1rem 0 1rem 1rem;

        svg {
          width: 45px;
          height: 45px;
        }
      }

      .overlay {
        display: block;
        position: fixed;
        top: 0;
        left: 0;
        width: 30%;
        height: 100vh;
      }

      nav {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 3rem;
        position: fixed;
        top: 0;
        right: 0;
        bottom: 0;
        width: 70%;
        height: 100vh;
        background: $color-secondary;
        flex-direction: column;
        transform: translateX(100%);
        transition: transform 0.3s ease-in-out;
        z-index: 2;

        &.open {
          transform: translateX(0);
        }

        .close {
          border: none;
          background: none;
          padding: 0;
          cursor: pointer;
          width: 30px;
          height: 30px;
          position: absolute;
          top: 0;
          right: 0;
          margin: 2rem 3rem 0 0;
        }

        .menu,
        .contact {
          width: 100%;
          display: flex;
          align-items: center;
          justify-content: center;
          margin: 0;

          a {
            color: $color-primary;
          }
        }

        .menu ul {
          flex-direction: column;
          gap: 0.5rem;

          li {
            text-align: center;
            margin: 1rem 0;

            a {
              font-size: 1.2rem;
              font-weight: 600;
              padding: 1rem 3rem;
              color: $color-primary;
            }
          }
        }
      }
    }
  }
}

.herobanner {
  height: calc(100vh - 104px);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 1.2rem;
  max-width: 100%;
  padding: 0 2rem;

  h2 {
    margin-bottom: 1rem;
  }

  p {
    color: $color-secondary;
    margin-bottom: 1rem;
    padding: 0 1rem;
    text-align: center;
  }

  a {
    margin: 0;
  }

  .scroll-icon {
    position: absolute;
    bottom: 0;
    right: 0;
    padding: 2.5rem;
    z-index: 1;
    width: 35px;
    height: 35px;
  }
}

@media (min-width: 1280px) {
  .herobanner {
    .scroll-icon {
      padding: 0rem;
    }

    .scroll-wrapper {
      position: absolute;
      bottom: 2rem;
      left: 50%;
      transform: translateX(-50%);
      width: 100%;
      max-width: 1200px;
      display: flex;
      justify-content: flex-end;
    }
  }
}
</style>