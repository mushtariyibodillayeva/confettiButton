//example-1
<!-- <script setup>
import HelloWorld from "./components/HelloWorld.vue";
import TheWelcome from "./components/TheWelcome.vue";
import CustomParticles from "./components/Particles.vue";
</script>

<template>
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="./assets/logo.svg"
      width="125"
      height="125"
    />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />
    <CustomParticles />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style> -->

//example-2 tsParticles Confetti
<template>
  <header>
    <ul class="nav-menu">
      <a href="#"
        ><img src="./assets/logo.svg" alt="logo" class="header-logo"
      /></a>
      <li class="nav-item">
        <a href="#" class="nav-link">Home</a>
      </li>
      <li class="nav-item">
        <a href="#" class="nav-link">About</a>
      </li>
      <li class="nav-item">
        <a href="#" class="nav-link">Contact</a>
      </li>
    </ul>
  </header>
  <div class="wrap">
    <h1>
      If you want to vote for our UzumMarket online store, click the button
      below!
    </h1>
    <button @click="handleClick" class="confetti-button">UzumMarket</button>
  </div>
</template>

<script>
import confetti from "canvas-confetti";
export default {
  name: "ConfettiButton",
  methods: {
    handleClick() {
      const duration = 10 * 1000,
        animationEnd = Date.now() + duration,
        defaults = { startVelocity: 30, spread: 360, ticks: 60, zIndex: 0 };

      function randomInRange(min, max) {
        return Math.random() * (max - min) + min;
      }

      const interval = setInterval(function () {
        const timeLeft = animationEnd - Date.now();

        if (timeLeft <= 0) {
          return clearInterval(interval);
        }

        const particleCount = 50 * (timeLeft / duration);

        // since particles fall down, start a bit higher than random
        confetti(
          Object.assign({}, defaults, {
            particleCount,
            origin: { x: randomInRange(0.1, 0.2), y: Math.random() - 0.2 },
          })
        );
        confetti(
          Object.assign({}, defaults, {
            particleCount,
            origin: { x: randomInRange(0.5, 0.9), y: Math.random() - 0.2 },
          })
        );
      }, 250);
    },
  },
};
</script>

<style scoped>
* {
  font-family: cursive;
}
body {
  background-color: aqua;
}
.confetti-button {
  background-color: green;
  color: aliceblue;
  border: none;
  padding: 20px 36px;
  border-radius: 20px 0 20px 0;
  font-size: 20px;
}

header {
  margin: 10px 0 100px 0;
  background: linear-gradient(to left, rgb(250, 177, 190), yellow);
  padding: 10px;
}
.nav-menu {
  display: flex;
  align-items: center;
  justify-content: space-around;
}
.nav-item {
  list-style-type: none;
}
.nav-link:hover {
  color: black;
}
.nav-link {
  text-decoration: none;
  font-size: 23px;
  color: blue;
}
h1 {
  color: crimson;
  width: 700px;
  border-right: 2.2px solid red;
}
.wrap {
  display: flex;
  align-items: center;
  justify-content: space-around;
}
</style>
