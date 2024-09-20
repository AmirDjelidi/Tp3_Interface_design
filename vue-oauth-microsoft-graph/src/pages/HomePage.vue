<template>
  <div>
    <h1>Il n'y a pas de bonne ou de mauvaise Vue 😉</h1>
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
  animation:rotation linear 5s infinite;
}


@keyframes rotation {
  0% {
    transform: translate(0, 200px) rotate(0deg);
  }
  25% {
    transform: translate(200px, 200px) rotate(90deg);
  }
  50% {
    transform: translate(400px, 200px) rotate(180deg);
  }
  75% {
    transform: translate(600px, 200px) rotate(270deg);
  }
  100% {
    transform: translate(800px, 200px) rotate(360deg);
  }
}
</style>
