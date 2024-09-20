<template>
  <div>
    <h1>Il n'y a pas de bonne ou de mauvaise Vue 😉</h1>
    <img src="../assets/astro.png" alt="Astro">
  </div>
  
</template>

<script>
export default {
  name: 'HomePage',
}
</script>

<style scoped>

h1 {
  text-align: center;
  font-family: "Bebas Neue", sans-serif;
  font-weight: 400;
  font-style: normal;
  position: absolute;
  color: white;

}

img{
  animation:rotation linear 5s infinite;
}


@keyframes rotation {
  0% {
    transform: translate(0, 10px) rotate(0deg);
  }
  25% {
    transform: translate(150px, 10px) rotate(90deg);
  }
  50% {
    transform: translate(300px, 10px) rotate(180deg);
  }
  75% {
    transform: translate(800px, 10px) rotate(270deg);
  }
  100% {
    transform: translate(1500px, 10px) rotate(360deg);
  }
}
</style>
