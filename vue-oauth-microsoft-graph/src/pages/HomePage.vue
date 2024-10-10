<template>
  <h1>Il n'y a pas de bonne ou de mauvaise Vue 😉</h1>
  <img src="../assets/otis.png" alt="otis" width="180px" height="180px" />
  <div class="center-container">
    <!-- Ce bouton sera désactivé après avoir été cliqué -->
    <BaseButton color="primary" disableOnClick>You can disable me !</BaseButton>

    <!-- Ces boutons ne seront pas désactivés après un clic -->
    <BaseButton color="primary">Primary Button </BaseButton>
    <BaseButton color="warn">Warn Button</BaseButton>
    <BaseButton color="danger">Danger Button</BaseButton>


  </div>
</template>

<script>
import BaseButton from "@/components/BaseButton.vue";


export default {
  name: 'HomePage',
  components: {BaseButton,},
}
</script>

<style scoped>
.center-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 70vh;
  gap: 20px;
}

h1 {
  margin-top: 80px;
  text-align: center;
  font-family: "Bebas Neue", sans-serif;
  font-weight: 400;
}

img {
  position: absolute;
  animation: rotation linear 5s infinite;
}

@keyframes rotation {
  0% {
    transform: translate(-200px, 0px) rotate(0deg);
  }
  100% {
    transform: translate(1500px, 0px) rotate(360deg);
  }
}
</style>
