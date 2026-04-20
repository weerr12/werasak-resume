<script setup lang="ts">
import { onMounted } from 'vue'

onMounted(() => {
  // @ts-ignore
  if (typeof particlesJS !== 'undefined') {
    // @ts-ignore
    particlesJS('particles-js', {
      particles: {
        number: {
          value: 60,
          density: {
            enable: true,
            value_area: 800,
          },
        },
        color: {
          value: '#6c63ff',
        },

        shape: {
          type: 'circle',
        },
        opacity: {
          value: 0.5,
          random: true,
          anim: {
            enable: false,
            speed: 1,
            opacity_min: 0.3,
            sync: false,
          },
        },
        size: {
          value: 2,
          random: true,
          anim: {
            enable: false,
            speed: 40,
            size_min: 1,
            sync: false,
          },
        },
        line_linked: {
          enable: true,
          distance: 150,
          color: '#6c63ff',
          opacity: 0.2,
          width: 1,
        },
        move: {
          enable: true,
          speed: 3,
          direction: 'none',
          random: true,
          straight: false,
          out_mode: 'out',
          bounce: false,
          attract: {
            enable: false,
            rotateX: 600,
            rotateY: 1200,
          },
        },
      },
      interactivity: {
        detect_on: 'window',
        events: {
          onhover: {
            enable: true,
            mode: 'repulse', // repulse the particles on mouse hover
          },
          onclick: {
            enable: true,
            mode: 'push', // adds the particles on click
          },
          resize: true,
        },
        modes: {
          grab: {
            distance: 400,
            line_linked: {
              opacity: 1,
            },
          },
          bubble: {
            distance: 400,
            size: 40,
            duration: 2,
            opacity: 8,
            speed: 3,
          },
          repulse: {
            distance: 300, // distance of the particles from the cursor
            duration: 0.4,
          },
          push: {
            particles_nb: 10, // number of particles to add on click
          },
          remove: {
            particles_nb: 2,
          },
        },
      },
      retina_detect: true,
    })
  }
})
</script>

<template>
  <div id="particles-js" class="fixed inset-0 pointer-events-none -z-10"></div>
</template>
