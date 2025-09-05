<template>
  <div class="projects-container">
    <div>
      <h2>Mes projets</h2>
      <div class="projects-list">
        <div 
          class="project"
          v-for="project in projects"
          :key="project.id"
          @mouseenter="onEnter($event.currentTarget, project)"
          @mouseleave="onLeave($event.currentTarget, project)"
        >
          <a href="#">
            <span>{{ project.number }}</span>
            <h3>{{ project.title }}</h3>
          </a>  

          <!-- Image placée à côté de ce projet -->
          <div 
            class="floating-project-image"
            v-if="hoveredProject === project.id"
            ref="floatingImage"
          >
            <img :src="project.image" :alt="project.title" ref="projectImage" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { gsap } from 'gsap'

const projects = ref([
  { id: 1, number: '01.', title: 'Qué bringue', image: '/images/pintes_athletes.png' },
  { id: 2, number: '02.', title: 'Les Pintes Athlètes', image: '/images/pintes_athletes.png' },
  { id: 3, number: '03.', title: 'Leonidas', image: '/images/leonidas.png' },
  { id: 4, number: '04.', title: 'Positive Mind Attitude', image: '/images/pintes_athletes.png' },
  { id: 5, number: '05.', title: 'Key Of Dreams', image: '/images/pintes_athletes.png' }
])

const hoveredProject = ref(null)
const floatingImage = ref(null)
const projectImage = ref(null)

let isAnimating = false

// Animation entrée projet
const onEnter = (el, project) => {
  hoveredProject.value = project.id

  // Projets non survolés → opacité réduite
  document.querySelectorAll('.project').forEach(p => {
    if (p !== el) {
      gsap.to(p, { opacity: 0.3, duration: 0.4, ease: "power2.out" })
    }
  })

  // Projet survolé → translation + zoom
  gsap.to(el, {
    x: 50,
    scale: 1.02,
    opacity: 1,
    duration: .6,
    ease: "power2.out"
  })
}

// Animation sortie projet
const onLeave = (el, project) => {
  hoveredProject.value = null

  // Tous les projets reviennent à leur état initial
  document.querySelectorAll('.project').forEach(p => {
    gsap.to(p, {
      x: 0,
      scale: 1,
      opacity: 0.3,
      duration: .3,
      ease: "power2.inOut"
    })
  })
}
</script>

<style lang="scss" scoped>
@use "@/styles/global.scss" as *;

.projects-container {
  background-color: $color-primary;
  padding: 10rem 2rem 6rem 2rem;

  > div {
    max-width: 100%;
    width: 1200px;
    margin: 0 auto;

    h2 {
      text-align: center;
      font-family: $font-secondary;
      font-size: 5rem;
      padding-bottom: 6rem;
    }
  }

  .projects-list {
    position: relative;
  }

  .project {
    position: relative;

    a {
      display: flex;
      align-items: center;
      padding: 1rem 0;
      gap: 2rem;
      margin: 2rem 0;
      cursor: pointer;
    }

    span {
      color: $color-secondary;
      font-weight: 300;
      font-size: clamp(.8rem, 3vw, 1rem);
      flex-shrink: 0;
    }

    h3 {
      font-family: $font-primary;
      font-size: clamp(1.8rem, 3vw, 5rem);
      font-weight: 500;
      flex: 1;
    }
  }

  .floating-project-image {
    position: absolute;
    top: -120%;
    right: 15%;
    width: 320px;
    height: 320px;
    pointer-events: none;
    z-index: 10;
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);

    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
    }
  }
}

@media (max-width: 768px) {
  .projects-container {
    padding: 5rem 1rem 3rem 1rem;

    > div h2 {
      font-size: 3rem;
      padding-bottom: 3rem;
    }

    .project {
      a {
        flex-direction: column;
        align-items: flex-start;
        gap: 1rem;
      }

      .project-image {
        width: 100%;
        height: 150px;
        align-self: center;
      }
    }
  }
}
</style>
