//example-1
<!-- <template>
  <Particles
    id="tsparticles"
    :options="options"
    :particlesInit="particlesInit"
  />
</template>

<script lang="ts">
import type { Engine } from "tsparticles-engine";
import { loadSlim } from "tsparticles-slim";
export default {
  data() {
    return {
      options: {
        background: {
          color: "#000",
        },
        fullScreen: {
          enable: true,
          zIndex: -1,
        },
        interactivity: {
          events: {
            onClick: {
              enable: true,
              mode: "push",
            },
            onHover: {
              enable: true,
              mode: "repulse",
            },
          },
          modes: {
            push: {
              quantity: 10,
            },
            repulse: {
              distance: 300,
            },
          },
        },
        particles: {
          links: {
            distance: 300,
            enable: true,
          },
          move: {
            enable: true,
            speed: { min: 1, max: 5 },
          },
          opacity: {
            value: { min: 0.3, max: 0.7 },
          },
          size: {
            value: { min: 1, max: 3 },
          },
        },
      },
    };
  },
  methods: {
    async particlesInit(engine: Engine) {
      await loadSlim(engine);
    },
  },
};
</script>

<style scoped></style> -->

//example-2
<!-- <template>
  <div id="app">
    <Particles
      id="tsparticles"
      :particlesInit="particlesInit"
      :particlesLoaded="particlesLoaded"
      :options="{
        background: {
          color: {
            value: '#000',
          },
        },
        fpsLimit: 120,
        interactivity: {
          events: {
            onClick: {
              enable: true,
              mode: 'push',
            },
            onHover: {
              enable: true,
              mode: 'repulse',
            },
            resize: true,
          },
          modes: {
            bubble: {
              distance: 400,
              duration: 2,
              opacity: 0.8,
              size: 40,
            },
            push: {
              quantity: 4,
            },
            repulse: {
              distance: 200,
              duration: 0.4,
            },
          },
        },
        particles: {
          color: {
            value: '#ffffff',
          },
          links: {
            color: '#ffffff',
            distance: 150,
            enable: true,
            opacity: 0.5,
            width: 1,
          },
          collisions: {
            enable: true,
          },
          move: {
            direction: 'none',
            enable: true,
            outMode: 'bounce',
            random: false,
            speed: 2,
            straight: false,
          },
          number: {
            density: {
              enable: true,
              area: 800,
            },
            value: 80,
          },
          opacity: {
            value: 0.5,
          },
          shape: {
            type: 'circle',
          },
          size: {
            random: true,
            value: 5,
          },
        },
        detectRetina: true,
      }"
    />
  </div>
</template>

<script setup>
import { loadFull } from "tsparticles";
const particlesInit = async (engine) => {
  await loadFull(engine);
};

const particlesLoaded = async (container) => {
  console.log("Particles container loaded", container);
};
</script>

<style scoped></style> -->
