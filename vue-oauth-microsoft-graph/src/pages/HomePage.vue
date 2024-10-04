<template>
    <h1>Il n'y a pas de bonne ou de mauvaise Vue 😉</h1>
    <img src="../assets/otis.png" alt="otis" width="180px" height="180px" />
    <div class="center-container">
      <BaseButton color="primary" />
      <BaseButton color="warn" />
      <BaseButton color="danger" />
    </div>
</template>

<script>
import BaseButton from "@/components/BaseButton.vue";

export default {
  name: 'HomePage',
  components: {BaseButton},
}
</script>

<style scoped>
.center-container {
  display: flex;
  justify-content: center;  /* Aligner les boutons côte à côte au centre */
  align-items: center;      /* Centrer les boutons verticalement */
  height: 70vh;            /* Prend toute la hauteur de l'écran */
  gap: 20px;                /* Espace de 20px entre les boutons */
}
h1 {
  margin-top: 80px;
  text-align: center;
  font-family: "Bebas Neue", sans-serif;
  font-weight: 400;
  font-style: normal;
  align-items: center;      /* Centrer les boutons verticalement */


}

img{
  position: absolute;
  animation:rotation linear 5s infinite;

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
